---
{"dg-publish":true,"permalink":"/3-permanent-notes/how-are-dependencies-tracked-in-go/","created":"2023-08-03 06:50","updated":"2023-08-04 07:00"}
---

#type/permanent #code/go 

---
We create a folder via go mod init and specify a path name like so
`go mod init folder/name`

go.mod file will list the dependencies that your project needs.
Must be similar to package.json

Dependencies listed point to your online repository. If you are developing local you need to update your go.mod file and replace the path like so: 
`replace example.com/greetings => ../greetings`


---
## Questions
## Terms

## References