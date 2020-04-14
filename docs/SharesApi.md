# unity_cloud_build.SharesApi

All URIs are relative to *https://localhost/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_share_metadata**](SharesApi.md#get_share_metadata) | **GET** /shares/{shareid} | Get details on shared build including download link


# **get_share_metadata**
> object get_share_metadata(shareid, include=include)

Get details on shared build including download link

This is an endpoint accessible without an api key that provides information about a specific build including download links. A shareid is generated by POSTing to a <a href=\"#!/builds/createShare\">build's share endpoint</a>.

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build
from unity_cloud_build.rest import ApiException
from pprint import pprint

# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure HTTP basic authorization: filetoken
configuration = unity_cloud_build.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = unity_cloud_build.SharesApi(unity_cloud_build.ApiClient(configuration))
shareid = 'shareid_example' # str | 
include = 'include_example' # str | Extra fields to include in the response (optional)

try:
    # Get details on shared build including download link
    api_response = api_instance.get_share_metadata(shareid, include=include)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling SharesApi->get_share_metadata: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **shareid** | **str**|  | 
 **include** | **str**| Extra fields to include in the response | [optional] 

### Return type

**object**

### Authorization

[apikey](../README.md#apikey), [filetoken](../README.md#filetoken)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
