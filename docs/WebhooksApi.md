# unity_cloud_build_api.WebhooksApi

All URIs are relative to */api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_hook_for_org**](WebhooksApi.md#add_hook_for_org) | **POST** /orgs/{orgid}/hooks | Add hook for organization
[**add_hook_for_project**](WebhooksApi.md#add_hook_for_project) | **POST** /orgs/{orgid}/projects/{projectid}/hooks | Add hook for project
[**delete_hook_for_org**](WebhooksApi.md#delete_hook_for_org) | **DELETE** /orgs/{orgid}/hooks/{id} | Delete organization hook
[**delete_hook_for_project**](WebhooksApi.md#delete_hook_for_project) | **DELETE** /orgs/{orgid}/projects/{projectid}/hooks/{id} | Delete project hook
[**get_hook_for_org**](WebhooksApi.md#get_hook_for_org) | **GET** /orgs/{orgid}/hooks/{id} | Get organization hook details
[**get_hook_for_project**](WebhooksApi.md#get_hook_for_project) | **GET** /orgs/{orgid}/projects/{projectid}/hooks/{id} | Get project hook details
[**list_hooks_for_org**](WebhooksApi.md#list_hooks_for_org) | **GET** /orgs/{orgid}/hooks | List hooks for organization
[**list_hooks_for_project**](WebhooksApi.md#list_hooks_for_project) | **GET** /orgs/{orgid}/projects/{projectid}/hooks | List hooks for project
[**ping_hook_for_org**](WebhooksApi.md#ping_hook_for_org) | **POST** /orgs/{orgid}/hooks/{id}/ping | Ping an org hook
[**ping_hook_for_project**](WebhooksApi.md#ping_hook_for_project) | **POST** /orgs/{orgid}/projects/{projectid}/hooks/{id}/ping | Ping a project hook
[**update_hook_for_org**](WebhooksApi.md#update_hook_for_org) | **PUT** /orgs/{orgid}/hooks/{id} | Update hook for organization
[**update_hook_for_project**](WebhooksApi.md#update_hook_for_project) | **PUT** /orgs/{orgid}/projects/{projectid}/hooks/{id} | Update hook for project

# **add_hook_for_org**
> object add_hook_for_org(orgid, body=body)

Add hook for organization

Adds a new organization level hook. An organization level hook is triggered by events from all projects belonging to the organziation. NOTE: you must be a manager in the organization to add new hooks. <h4>Hook Type Configuration Parameters</h4> <div class=\"webhook-tag-desc\"> <table> <tr><th>Type</th><th>Configuration Options</th></tr> <tr>    <td><code>web</code>    <td>       <table>          <tr><th>url</th><td>Endpoint to submit POST request</td></tr>          <tr><th>encoding</th><td>Either <code>json</code> (default) or <code>form</code></td></tr>          <tr><th>sslVerify</th><td>Verify SSL certificates of HTTPS endpoint</td></tr>          <tr><th>secret</th><td>Used to compute the SHA256 HMAC signature of the hook body and adds          a <code>X-UnityCloudBuild-Signature</code> header to the payload</td></tr>       </table>    </td> </tr> <tr>    <td><code>slack</code>    <td>       <table>          <tr><th>url</th><td>Slack incoming webhook URL. Learn more at https://api.slack.com/incoming-webhooks</td></tr>       </table>    </td> </tr> </table> </div> 

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
body = unity_cloud_build_api.OrgidHooksBody() # OrgidHooksBody |  (optional)

try:
    # Add hook for organization
    api_response = api_instance.add_hook_for_org(orgid, body=body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->add_hook_for_org: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **body** | [**OrgidHooksBody**](OrgidHooksBody.md)|  | [optional] 

### Return type

**object**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **add_hook_for_project**
> object add_hook_for_project(orgid, projectid, body=body)

Add hook for project

Adds a new project level hook. A project level hook is only triggered by events from the specific project. NOTE: you must be a manager in the organization to add new hooks. <h4>Hook Type Configuration Parameters</h4> <div class=\"webhook-tag-desc\"> <table> <tr><th>Type</th><th>Configuration Options</th></tr> <tr>    <td><code>web</code>    <td>       <table>          <tr><th>url</th><td>Endpoint to submit POST request</td></tr>          <tr><th>encoding</th><td>Either <code>json</code> (default) or <code>form</code></td></tr>          <tr><th>sslVerify</th><td>Verify SSL certificates of HTTPS endpoint</td></tr>          <tr><th>secret</th><td>Used to compute the SHA256 HMAC signature of the hook body and adds          a <code>X-UnityCloudBuild-Signature</code> header to the payload</td></tr>       </table>    </td> </tr> <tr>    <td><code>slack</code>    <td>       <table>          <tr><th>url</th><td>Slack incoming webhook URL. Learn more at https://api.slack.com/incoming-webhooks</td></tr>       </table>    </td> </tr> </table> </div> 

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
projectid = 'projectid_example' # str | Project identifier
body = unity_cloud_build_api.ProjectidHooksBody() # ProjectidHooksBody |  (optional)

try:
    # Add hook for project
    api_response = api_instance.add_hook_for_project(orgid, projectid, body=body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->add_hook_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **projectid** | **str**| Project identifier | 
 **body** | [**ProjectidHooksBody**](ProjectidHooksBody.md)|  | [optional] 

### Return type

**object**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_hook_for_org**
> str delete_hook_for_org(orgid, id)

Delete organization hook

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
id = 'id_example' # str | Hook record identifier

try:
    # Delete organization hook
    api_response = api_instance.delete_hook_for_org(orgid, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->delete_hook_for_org: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **id** | **str**| Hook record identifier | 

### Return type

**str**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_hook_for_project**
> str delete_hook_for_project(orgid, projectid, id)

Delete project hook

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
projectid = 'projectid_example' # str | Project identifier
id = 'id_example' # str | Hook record identifier

try:
    # Delete project hook
    api_response = api_instance.delete_hook_for_project(orgid, projectid, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->delete_hook_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **projectid** | **str**| Project identifier | 
 **id** | **str**| Hook record identifier | 

### Return type

**str**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_hook_for_org**
> object get_hook_for_org(orgid, id)

Get organization hook details

Get details of a hook by id

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
id = 'id_example' # str | Hook record identifier

try:
    # Get organization hook details
    api_response = api_instance.get_hook_for_org(orgid, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->get_hook_for_org: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **id** | **str**| Hook record identifier | 

### Return type

**object**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_hook_for_project**
> object get_hook_for_project(orgid, projectid, id)

Get project hook details

Get details of a hook by id

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
projectid = 'projectid_example' # str | Project identifier
id = 'id_example' # str | Hook record identifier

try:
    # Get project hook details
    api_response = api_instance.get_hook_for_project(orgid, projectid, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->get_hook_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **projectid** | **str**| Project identifier | 
 **id** | **str**| Hook record identifier | 

### Return type

**object**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_hooks_for_org**
> list[InlineResponse2005] list_hooks_for_org(orgid)

List hooks for organization

List all hooks configured for the specified organization

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier

try:
    # List hooks for organization
    api_response = api_instance.list_hooks_for_org(orgid)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->list_hooks_for_org: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 

### Return type

[**list[InlineResponse2005]**](InlineResponse2005.md)

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_hooks_for_project**
> list[InlineResponse2005] list_hooks_for_project(orgid, projectid)

List hooks for project

List all hooks configured for the specified project

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
projectid = 'projectid_example' # str | Project identifier

try:
    # List hooks for project
    api_response = api_instance.list_hooks_for_project(orgid, projectid)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->list_hooks_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **projectid** | **str**| Project identifier | 

### Return type

[**list[InlineResponse2005]**](InlineResponse2005.md)

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **ping_hook_for_org**
> str ping_hook_for_org(orgid, id)

Ping an org hook

Send a ping event to an org hook. 

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
id = 'id_example' # str | Hook record identifier

try:
    # Ping an org hook
    api_response = api_instance.ping_hook_for_org(orgid, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->ping_hook_for_org: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **id** | **str**| Hook record identifier | 

### Return type

**str**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **ping_hook_for_project**
> str ping_hook_for_project(orgid, projectid, id)

Ping a project hook

Send a ping event to a project hook. 

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
projectid = 'projectid_example' # str | Project identifier
id = 'id_example' # str | Hook record identifier

try:
    # Ping a project hook
    api_response = api_instance.ping_hook_for_project(orgid, projectid, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->ping_hook_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **projectid** | **str**| Project identifier | 
 **id** | **str**| Hook record identifier | 

### Return type

**str**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_hook_for_org**
> object update_hook_for_org(orgid, id, body=body)

Update hook for organization

Update a new hook. NOTE: you must be a manager in the organization to update hooks. 

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
id = 'id_example' # str | Hook record identifier
body = unity_cloud_build_api.HooksIdBody() # HooksIdBody |  (optional)

try:
    # Update hook for organization
    api_response = api_instance.update_hook_for_org(orgid, id, body=body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->update_hook_for_org: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **id** | **str**| Hook record identifier | 
 **body** | [**HooksIdBody**](HooksIdBody.md)|  | [optional] 

### Return type

**object**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_hook_for_project**
> object update_hook_for_project(orgid, projectid, id, body=body)

Update hook for project

Update an existing hook. NOTE: you must be a manager of the project to update hooks. 

### Example
```python
from __future__ import print_function
import time
import unity_cloud_build_api
from unity_cloud_build_api.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: apikey
configuration = unity_cloud_build_api.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'
# Configure OAuth2 access token for authorization: permissions
configuration = unity_cloud_build_api.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# create an instance of the API class
api_instance = unity_cloud_build_api.WebhooksApi(unity_cloud_build_api.ApiClient(configuration))
orgid = 'orgid_example' # str | Organization identifier
projectid = 'projectid_example' # str | Project identifier
id = 'id_example' # str | Hook record identifier
body = unity_cloud_build_api.HooksIdBody1() # HooksIdBody1 |  (optional)

try:
    # Update hook for project
    api_response = api_instance.update_hook_for_project(orgid, projectid, id, body=body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->update_hook_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **orgid** | **str**| Organization identifier | 
 **projectid** | **str**| Project identifier | 
 **id** | **str**| Hook record identifier | 
 **body** | [**HooksIdBody1**](HooksIdBody1.md)|  | [optional] 

### Return type

**object**

### Authorization

[apikey](../README.md#apikey), [permissions](../README.md#permissions)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, text/plain, text/html, text/csv

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

