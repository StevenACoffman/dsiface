# dsifake
Google Cloud Platform datastore interface fake

### Why do I want this?
If you interact with Google Cloud Datastore (firebase in datastore mode) in Go, and you have read
(testing guid)[https://github.com/googleapis/google-cloud-go/blob/master/testing.md]

TLDR; You can fake /w grpc.Server. Or define your own interface for methods you use and mock it. This is the latter.

### Where did you (mostly) steal this?

There are already some mock/fake implementations for Get, Put, etc., but not GetMulti:
+ (m-lab/go/cloudtest)[https://pkg.go.dev/github.com/m-lab/go/cloudtest/dsfake]
+ (go build/internal/datastore)[https://github.com/golang/build/tree/master/internal/datastore/fake]

### Your unit test is kinda ... gross?

This whole thing *is* for unit testing, so I didn't spend time 
making my unit testing *of the unit testing fixture* glorious. Got a better idea? Pull Requests welcome.