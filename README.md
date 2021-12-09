# buf build example
What I want:
`protoc -I . --go_out=. --go_opt=module=example.com subproj1/moduleA/*.proto`

And subproj1/moduleA/pb1/pb1.pb.go:
```go
// source: subproj1/moduleA/pb1.proto
```

---
However
If I use bufbuild with buf.work.yaml, run `buf generate` or `buf generate subproj1/moduleA`, I got:
```go
// source: pb1.proto
```

---
I know I can remove `buf.work.yaml` and `subproj1/moduleA/buf.yaml` then run `buf generate --path subproj1/moduleA` and it works.
But I can't include dependencies or exclude file in moduleA if i did this.