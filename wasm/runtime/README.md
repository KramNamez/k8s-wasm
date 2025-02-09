# WASM Runtime

This repository implements multiple data passing mechanisms for multiple WASM runtimes with Go.

For each runtime and for each data passing mechanism we implement the RawRunner interface if possible.
The RawRunner interface describes that we want to call a certain function `fnName` in the module and pass the raw bytes `input` to the call.
As return value we get back raw bytes `output` or an error `err` if the call of the function in the module failed.
```
type RawRunner interface {
	Run(ctx context.Context, fnName string, input []byte) (output []byte, err error)
}
```

Before you run the tests in this repository you have to build the [test modules](../modules/rs/).

Then you can run the tests:
```
go test -v
```
