# filesystem-wrapper
Library for using the Chrome specific Filesystem API.

Some code is from https://github.com/FoxMoss/FoxLauncher/

map:

openFS()

starts the filesystem process and makes it so writing makes a bit more sense

makeFile()

makes a file, with content

writeFile()

(over)writes [to] an existing file

deleteFile()

incase this is necessary for what you're trying to do

getFile()

gets file content

finishFS(callback: filesystem url)

will return a filesystem url which defaults to index.html if it was created/exists, this does the actual `webkitRequestFileSystem` stuff. this means until finishFS, nothing within the filesystem exists because it literally was not created.

> the writer and everything will be handled by the library cus its annoying