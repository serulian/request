# XHR Request Library

## Example Usage

```seru
from "github.com/Serulian/request:master" import GetURLContents, Post, Delete

function<void> MakeRequests() {
	// Retrieve the contents of the specified URL. Will wait until the request
	// returns. If the response has a non-2XX error code, will reject with an
	// HttpError.
	var data = GetURLContents('http://some/url')

	_, failed := Post('http://some/other/url', data).RejectOnFailure()
	if failed is not null {
		// Something went wrong with the post.
	}
}
```