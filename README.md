# filesystem-wrapper
Library for using the Chrome specific Filesystem API.

Files will persist until data for the website that the filesystem is opened within is cleared. Furthermore, you can actually VISIT/run files (ex. creating an index.html file) and html files can use other created files as assets normally within the filesystem environment. you can use these files without internet. so essentially this is a library to create files that can be visited locally, with https permissions.

## important: limitations

for some reason, links to other filesystem:// urls can't be clicked so if you have other html files within the system and you're trying to link them it won't work you'll have to direct users to do ctrl + click (basically target="_blank" but more annoying) 

IDK about this but you might be able to overwrite body and replace it with the new html file's content so upon click the user will see new content. it will be annoying most likely.

## map:

`makeFile()`

makes a file, with content

`writeFile()`

(over)writes [to] an existing file

`deleteFile()`

incase this is necessary for what you're trying to do

`getFile()`

gets file content

`getFiles(prefix, suffix)`

get existing files, you can filter through files with prefix/suffix. actual file data (file names, directories, ect) will be stored in localstorage 

`massFS([{file, action}, {file, action}])`

mass write/read files etc. useful when you load many files from storage.

internal (not to be used by the client, but the library to make development easier):

`openFS()`

starts the filesystem process and makes it so writing makes a bit more sense... this is literally only for storage purposes nothing is actually happening other than stuff being stored or some shi idk openFS could also be used for starting the rw process after closing

`finishFS()`

 this does the actual `webkitRequestFileSystem` stuff. this means until finishFS, nothing within the filesystem exists because it literally was not created.


makeFile()

main way to create, modify content within a file

> the writer and everything will be handled by the library cus its annoying, besides, whats the point of this if you need to do allat

## credits

doxr

Some code is from https://github.com/FoxMoss/FoxLauncher/