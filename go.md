# GO

## Version updates

Upon the release of a new version of Go, all repositories are updated
according to the following conventions:
* The minimum supported version of Go is set to one version back from
  the current one. For example, upon the release of Go 1.22, the minimum
  version becomes 1.21 (just like Go itself, release 1.22 makes 1.20
  unsupported).
* All dependency packages are updated (sometimes, according to project 
  requirements, some deprecated package methods may be updated as well.)
* New Go version features are adapted where they make sense or can improve 
  performance.
* Go versions in GitHub workflows are also updated as follows:

  1. Testing is performed for the last two versions of Go. In the example
  mentioned above, this would be `[ '1.21', '1.22' ]`.
  2. For build and cover jobs, the latest version should be used. In the 
  example mentioned above, this would be 1.22. 
  3. If there are new versions of GitHub actions, they can also be updated 
  (for example, actions/checkout, actions/setup-go, actions/upload-artifact, 
  etc.).
  4. The Go version for the linter equals the minimum supported version and 
  is usually taken from the `go.mod` file by specifying in the *.yml file:
  ```        
  with:
    go-version-file: 'go.mod'
  ```
