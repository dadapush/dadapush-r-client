# DaDaPushMessageApi

All URIs are relative to *https://www.dadapush.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateMessage**](DaDaPushMessageApi.md#CreateMessage) | **POST** /api/v1/message | push Message to a Channel
[**DeleteMessage**](DaDaPushMessageApi.md#DeleteMessage) | **DELETE** /api/v1/message/{messageId} | delete a Channel Message
[**GetMessage**](DaDaPushMessageApi.md#GetMessage) | **GET** /api/v1/message/{messageId} | get a Channel Message
[**GetMessages**](DaDaPushMessageApi.md#GetMessages) | **GET** /api/v1/messages | get Message List


# **CreateMessage**
> ResultOfMessagePushResponse CreateMessage(body, x.channel.token=var.x.channel.token)

push Message to a Channel

<h2>Rate Limit:</h2><ul><li>1 request per 1s</li><li>30 request per 1m</li><li>500 request per 1h</li></ul><h2>Result code/errmsg List:</h2><ul><li>0: ok</li><li>1: server error</li><li>101: channel is exists</li><li>102: channel is not exists</li><li>103: channel token error</li><li>104: channel is not exists</li><li>105: message is not exists</li><li>204: bad request</li><li>205: permission deny</li><li>206: too many request, please after 5 minutes to try!</li><li>301: duplicate username/email</li><li>302: user is not exists</li><li>303: user password is error</li><li>304: client push token is error</li><li>305: user is disabled</li><li>306: your subscription is expired</li><li>307: user not subscribe channel</li></ul>

### Example
```R
library(DaDaPushClient)

var.body <- MessagePushRequest$new(list(Action$new("name_example", "type_example", "url_example")), "content_example", "needPush_example", "title_example") # MessagePushRequest | body
var.x.channel.token <- 'x.channel.token_example' # character | see: https://www.dadapush.com/channel/list

#push Message to a Channel
api.instance <- DaDaPushMessageApi$new()
result <- api.instance$CreateMessage(var.body, x.channel.token=var.x.channel.token)
dput(result)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**MessagePushRequest**](MessagePushRequest.md)| body | 
 **x.channel.token** | **character**| see: https://www.dadapush.com/channel/list | [optional] 

### Return type

[**ResultOfMessagePushResponse**](resultOfMessagePushResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **DeleteMessage**
> Result DeleteMessage(message.id, x.channel.token=var.x.channel.token)

delete a Channel Message

<h2>Rate Limit:</h2><ul><li>10 request per 1s</li><li>100 request per 1m</li><li>1000 request per 1h</li></ul><h2>Result code/errmsg List:</h2><ul><li>0: ok</li><li>1: server error</li><li>101: channel is exists</li><li>102: channel is not exists</li><li>103: channel token error</li><li>104: channel is not exists</li><li>105: message is not exists</li><li>204: bad request</li><li>205: permission deny</li><li>206: too many request, please after 5 minutes to try!</li><li>301: duplicate username/email</li><li>302: user is not exists</li><li>303: user password is error</li><li>304: client push token is error</li><li>305: user is disabled</li><li>306: your subscription is expired</li><li>307: user not subscribe channel</li></ul>

### Example
```R
library(DaDaPushClient)

var.message.id <- 56 # integer | messageId
var.x.channel.token <- 'x.channel.token_example' # character | see: https://www.dadapush.com/channel/list

#delete a Channel Message
api.instance <- DaDaPushMessageApi$new()
result <- api.instance$DeleteMessage(var.message.id, x.channel.token=var.x.channel.token)
dput(result)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **message.id** | **integer**| messageId | 
 **x.channel.token** | **character**| see: https://www.dadapush.com/channel/list | [optional] 

### Return type

[**Result**](result.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **GetMessage**
> ResultOfMessageObject GetMessage(message.id, x.channel.token=var.x.channel.token)

get a Channel Message

<h2>Rate Limit:</h2><ul><li>10 request per 1s</li><li>100 request per 1m</li><li>1000 request per 1h</li></ul><h2>Result code/errmsg List:</h2><ul><li>0: ok</li><li>1: server error</li><li>101: channel is exists</li><li>102: channel is not exists</li><li>103: channel token error</li><li>104: channel is not exists</li><li>105: message is not exists</li><li>204: bad request</li><li>205: permission deny</li><li>206: too many request, please after 5 minutes to try!</li><li>301: duplicate username/email</li><li>302: user is not exists</li><li>303: user password is error</li><li>304: client push token is error</li><li>305: user is disabled</li><li>306: your subscription is expired</li><li>307: user not subscribe channel</li></ul>

### Example
```R
library(DaDaPushClient)

var.message.id <- 56 # integer | messageId
var.x.channel.token <- 'x.channel.token_example' # character | see: https://www.dadapush.com/channel/list

#get a Channel Message
api.instance <- DaDaPushMessageApi$new()
result <- api.instance$GetMessage(var.message.id, x.channel.token=var.x.channel.token)
dput(result)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **message.id** | **integer**| messageId | 
 **x.channel.token** | **character**| see: https://www.dadapush.com/channel/list | [optional] 

### Return type

[**ResultOfMessageObject**](resultOfMessageObject.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **GetMessages**
> ResultOfPageResponseOfMessageObject GetMessages(page, page.size, x.channel.token=var.x.channel.token)

get Message List

<h2>Rate Limit:</h2><ul><li>1 request per 1s</li><li>45 request per 1m</li></ul><h2>Result code/errmsg List:</h2><ul><li>0: ok</li><li>1: server error</li><li>101: channel is exists</li><li>102: channel is not exists</li><li>103: channel token error</li><li>104: channel is not exists</li><li>105: message is not exists</li><li>204: bad request</li><li>205: permission deny</li><li>206: too many request, please after 5 minutes to try!</li><li>301: duplicate username/email</li><li>302: user is not exists</li><li>303: user password is error</li><li>304: client push token is error</li><li>305: user is disabled</li><li>306: your subscription is expired</li><li>307: user not subscribe channel</li></ul>

### Example
```R
library(DaDaPushClient)

var.page <- 1 # integer | greater than 1
var.page.size <- 10 # integer | range is 1,50
var.x.channel.token <- 'x.channel.token_example' # character | see: https://www.dadapush.com/channel/list

#get Message List
api.instance <- DaDaPushMessageApi$new()
result <- api.instance$GetMessages(var.page, var.page.size, x.channel.token=var.x.channel.token)
dput(result)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **integer**| greater than 1 | [default to 1]
 **page.size** | **integer**| range is 1,50 | [default to 10]
 **x.channel.token** | **character**| see: https://www.dadapush.com/channel/list | [optional] 

### Return type

[**ResultOfPageResponseOfMessageObject**](resultOfPageResponseOfMessageObject.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



