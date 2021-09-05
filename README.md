# dsifake
Google Cloud Platform datastore gRPC fake

### Why do I want this?
If you interact with Google Cloud Datastore (firebase in datastore mode) in Go, and you have read
(testing guid)[https://github.com/googleapis/google-cloud-go/blob/master/testing.md]

TLDR; You can fake /w grpc.Server. Or define your own interface for methods you use and mock it. This is the former.

We used to mock things, but when [googleapis/google-cloud-go-testing](https://github.com/googleapis/google-cloud-go-testing) 
got archived, we figured that was no longer a safe bet.

An emulator is great for integration tests. I just hate integration tests, so this is for unit tests.

### Where did you (mostly) steal this?

There were already some mock (not fake) implementations for Get, Put, etc., but not GetMulti:
+ (m-lab/go/cloudtest)[https://pkg.go.dev/github.com/m-lab/go/cloudtest/dsfake]
+ (go build/internal/datastore)[https://github.com/golang/build/tree/master/internal/datastore/fake]

### Your unit test is kinda ... gross?

This whole thing *is* for unit testing, so I didn't spend time 
making my unit testing *of the unit testing fixture* glorious. Got a better idea? Pull Requests welcome.