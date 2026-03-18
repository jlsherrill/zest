# \ApiSimpleAPI

All URIs are relative to *http://localhost:8080*

Method | HTTP request | Description
------------- | ------------- | -------------
[**ApiPypiSimpleCreate**](ApiSimpleAPI.md#ApiPypiSimpleCreate) | **Post** /api/pypi/{pulp_domain}/{path}/simple/ | Upload a package
[**ApiPypiSimpleRead**](ApiSimpleAPI.md#ApiPypiSimpleRead) | **Get** /api/pypi/{pulp_domain}/{path}/simple/ | Get index simple page
[**PypiSimplePackageRead**](ApiSimpleAPI.md#PypiSimplePackageRead) | **Get** /api/pypi/{pulp_domain}/{path}/simple/{package}/ | Get package simple page



## ApiPypiSimpleCreate

> PackageUploadTaskResponse ApiPypiSimpleCreate(ctx, path, pulpDomain).Content(content).Sha256Digest(sha256Digest).XTaskDiagnostics(xTaskDiagnostics).Action(action).ProtocolVersion(protocolVersion).Filetype(filetype).MetadataVersion(metadataVersion).Attestations(attestations).Execute()

Upload a package



### Example

```go
package main

import (
	"context"
	"fmt"
	"os"
	openapiclient "github.com/content-services/zest/release/v2024"
)

func main() {
	path := "path_example" // string | 
	pulpDomain := "pulpDomain_example" // string | 
	content := os.NewFile(1234, "some_file") // *os.File | A Python package release file to upload to the index.
	sha256Digest := "sha256Digest_example" // string | SHA256 of package to validate upload integrity.
	xTaskDiagnostics := []string{"Inner_example"} // []string | List of profilers to use on tasks. (optional)
	action := "action_example" // string | Defaults to `file_upload`, don't change it or request will fail! (optional) (default to "file_upload")
	protocolVersion := openapiclient.ProtocolVersionEnum(1) // ProtocolVersionEnum | Protocol version to use for the upload. Only version 1 is supported.* `1` - 1 (optional) (default to 1)
	filetype := openapiclient.FiletypeEnum("bdist_wheel") // FiletypeEnum | Type of artifact to upload.* `bdist_wheel` - bdist_wheel* `sdist` - sdist (optional)
	metadataVersion := openapiclient.MetadataVersionEnum("1.0") // MetadataVersionEnum | Metadata version of the uploaded package.* `1.0` - 1.0* `1.1` - 1.1* `1.2` - 1.2* `2.0` - 2.0* `2.1` - 2.1* `2.2` - 2.2* `2.3` - 2.3* `2.4` - 2.4 (optional)
	attestations := TODO // interface{} | A JSON list containing attestations for the package. (optional)

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	resp, r, err := apiClient.ApiSimpleAPI.ApiPypiSimpleCreate(context.Background(), path, pulpDomain).Content(content).Sha256Digest(sha256Digest).XTaskDiagnostics(xTaskDiagnostics).Action(action).ProtocolVersion(protocolVersion).Filetype(filetype).MetadataVersion(metadataVersion).Attestations(attestations).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `ApiSimpleAPI.ApiPypiSimpleCreate``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
	// response from `ApiPypiSimpleCreate`: PackageUploadTaskResponse
	fmt.Fprintf(os.Stdout, "Response from `ApiSimpleAPI.ApiPypiSimpleCreate`: %v\n", resp)
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**path** | **string** |  | 
**pulpDomain** | **string** |  | 

### Other Parameters

Other parameters are passed through a pointer to a apiApiPypiSimpleCreateRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **content** | ***os.File** | A Python package release file to upload to the index. | 
 **sha256Digest** | **string** | SHA256 of package to validate upload integrity. | 
 **xTaskDiagnostics** | **[]string** | List of profilers to use on tasks. | 
 **action** | **string** | Defaults to &#x60;file_upload&#x60;, don&#39;t change it or request will fail! | [default to &quot;file_upload&quot;]
 **protocolVersion** | [**ProtocolVersionEnum**](ProtocolVersionEnum.md) | Protocol version to use for the upload. Only version 1 is supported.* &#x60;1&#x60; - 1 | [default to 1]
 **filetype** | [**FiletypeEnum**](FiletypeEnum.md) | Type of artifact to upload.* &#x60;bdist_wheel&#x60; - bdist_wheel* &#x60;sdist&#x60; - sdist | 
 **metadataVersion** | [**MetadataVersionEnum**](MetadataVersionEnum.md) | Metadata version of the uploaded package.* &#x60;1.0&#x60; - 1.0* &#x60;1.1&#x60; - 1.1* &#x60;1.2&#x60; - 1.2* &#x60;2.0&#x60; - 2.0* &#x60;2.1&#x60; - 2.1* &#x60;2.2&#x60; - 2.2* &#x60;2.3&#x60; - 2.3* &#x60;2.4&#x60; - 2.4 | 
 **attestations** | [**interface{}**](interface{}.md) | A JSON list containing attestations for the package. | 

### Return type

[**PackageUploadTaskResponse**](PackageUploadTaskResponse.md)

### Authorization

[basicAuth](../README.md#basicAuth), [cookieAuth](../README.md#cookieAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data, application/x-www-form-urlencoded
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ApiPypiSimpleRead

> ApiPypiSimpleRead(ctx, path, pulpDomain).XTaskDiagnostics(xTaskDiagnostics).Format(format).Fields(fields).ExcludeFields(excludeFields).Execute()

Get index simple page



### Example

```go
package main

import (
	"context"
	"fmt"
	"os"
	openapiclient "github.com/content-services/zest/release/v2024"
)

func main() {
	path := "path_example" // string | 
	pulpDomain := "pulpDomain_example" // string | 
	xTaskDiagnostics := []string{"Inner_example"} // []string | List of profilers to use on tasks. (optional)
	format := "format_example" // string |  (optional)
	fields := []string{"Inner_example"} // []string | A list of fields to include in the response. (optional)
	excludeFields := []string{"Inner_example"} // []string | A list of fields to exclude from the response. (optional)

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	r, err := apiClient.ApiSimpleAPI.ApiPypiSimpleRead(context.Background(), path, pulpDomain).XTaskDiagnostics(xTaskDiagnostics).Format(format).Fields(fields).ExcludeFields(excludeFields).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `ApiSimpleAPI.ApiPypiSimpleRead``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**path** | **string** |  | 
**pulpDomain** | **string** |  | 

### Other Parameters

Other parameters are passed through a pointer to a apiApiPypiSimpleReadRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **xTaskDiagnostics** | **[]string** | List of profilers to use on tasks. | 
 **format** | **string** |  | 
 **fields** | **[]string** | A list of fields to include in the response. | 
 **excludeFields** | **[]string** | A list of fields to exclude from the response. | 

### Return type

 (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth), [cookieAuth](../README.md#cookieAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## PypiSimplePackageRead

> PypiSimplePackageRead(ctx, package_, path, pulpDomain).XTaskDiagnostics(xTaskDiagnostics).Format(format).Fields(fields).ExcludeFields(excludeFields).Execute()

Get package simple page



### Example

```go
package main

import (
	"context"
	"fmt"
	"os"
	openapiclient "github.com/content-services/zest/release/v2024"
)

func main() {
	package_ := "package__example" // string | 
	path := "path_example" // string | 
	pulpDomain := "pulpDomain_example" // string | 
	xTaskDiagnostics := []string{"Inner_example"} // []string | List of profilers to use on tasks. (optional)
	format := "format_example" // string |  (optional)
	fields := []string{"Inner_example"} // []string | A list of fields to include in the response. (optional)
	excludeFields := []string{"Inner_example"} // []string | A list of fields to exclude from the response. (optional)

	configuration := openapiclient.NewConfiguration()
	apiClient := openapiclient.NewAPIClient(configuration)
	r, err := apiClient.ApiSimpleAPI.PypiSimplePackageRead(context.Background(), package_, path, pulpDomain).XTaskDiagnostics(xTaskDiagnostics).Format(format).Fields(fields).ExcludeFields(excludeFields).Execute()
	if err != nil {
		fmt.Fprintf(os.Stderr, "Error when calling `ApiSimpleAPI.PypiSimplePackageRead``: %v\n", err)
		fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", r)
	}
}
```

### Path Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**package_** | **string** |  | 
**path** | **string** |  | 
**pulpDomain** | **string** |  | 

### Other Parameters

Other parameters are passed through a pointer to a apiPypiSimplePackageReadRequest struct via the builder pattern


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------



 **xTaskDiagnostics** | **[]string** | List of profilers to use on tasks. | 
 **format** | **string** |  | 
 **fields** | **[]string** | A list of fields to include in the response. | 
 **excludeFields** | **[]string** | A list of fields to exclude from the response. | 

### Return type

 (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth), [cookieAuth](../README.md#cookieAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

