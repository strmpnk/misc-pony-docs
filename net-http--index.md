This package includes all the support functions necessary to build client
and server applications for the HTTP protocol.

The important interfaces an application needs to deal with are:

* [HTTPSession](net-http-HTTPSession), the API to an HTTP connection.

* [HTTPHandler](net-http-HTTPHandler), the interface to a handler you
need to write that will receive notifications from the `HTTPSession`.

* [HandlerFactory](net-http-HandlerFactory), the interface to a class you
need to write that creates instances of your `HTTPHandler`.

* [Payload](net-http-Payload), the class that represents a single HTTP
message, with its headers.

If you are writing a client, you will need to deal with the
[HTTPClient](net-http-HTTPClient) class.

If you are writing a server, you will need to deal with the
[HTTPServer](net-http-HTTPServer) class.



## Public Types

* [primitive URLPartUser](net-http-URLPartUser.md)
* [primitive URLPartPassword](net-http-URLPartPassword.md)
* [primitive URLPartHost](net-http-URLPartHost.md)
* [primitive URLPartPath](net-http-URLPartPath.md)
* [primitive URLPartQuery](net-http-URLPartQuery.md)
* [primitive URLPartFragment](net-http-URLPartFragment.md)
* [type URLPart](net-http-URLPart.md)
* [primitive URLEncode](net-http-URLEncode.md)
* [class URL](net-http-URL.md)
* [trait Status](net-http-Status.md)
* [primitive StatusContinue](net-http-StatusContinue.md)
* [primitive StatusSwitchingProtocols](net-http-StatusSwitchingProtocols.md)
* [primitive StatusOK](net-http-StatusOK.md)
* [primitive StatusCreated](net-http-StatusCreated.md)
* [primitive StatusAccepted](net-http-StatusAccepted.md)
* [primitive StatusNonAuthoritativeInfo](net-http-StatusNonAuthoritativeInfo.md)
* [primitive StatusNoContent](net-http-StatusNoContent.md)
* [primitive StatusResetContent](net-http-StatusResetContent.md)
* [primitive StatusPartialContent](net-http-StatusPartialContent.md)
* [primitive StatusMultipleChoices](net-http-StatusMultipleChoices.md)
* [primitive StatusMovedPermanently](net-http-StatusMovedPermanently.md)
* [primitive StatusFound](net-http-StatusFound.md)
* [primitive StatusSeeOther](net-http-StatusSeeOther.md)
* [primitive StatusNotModified](net-http-StatusNotModified.md)
* [primitive StatusUseProxy](net-http-StatusUseProxy.md)
* [primitive StatusTemporaryRedirect](net-http-StatusTemporaryRedirect.md)
* [primitive StatusBadRequest](net-http-StatusBadRequest.md)
* [primitive StatusUnauthorized](net-http-StatusUnauthorized.md)
* [primitive StatusPaymentRequired](net-http-StatusPaymentRequired.md)
* [primitive StatusForbidden](net-http-StatusForbidden.md)
* [primitive StatusNotFound](net-http-StatusNotFound.md)
* [primitive StatusMethodNotAllowed](net-http-StatusMethodNotAllowed.md)
* [primitive StatusNotAcceptable](net-http-StatusNotAcceptable.md)
* [primitive StatusProxyAuthRequired](net-http-StatusProxyAuthRequired.md)
* [primitive StatusRequestTimeout](net-http-StatusRequestTimeout.md)
* [primitive StatusConflict](net-http-StatusConflict.md)
* [primitive StatusGone](net-http-StatusGone.md)
* [primitive StatusLengthRequired](net-http-StatusLengthRequired.md)
* [primitive StatusPreconditionFailed](net-http-StatusPreconditionFailed.md)
* [primitive StatusRequestEntityTooLarge](net-http-StatusRequestEntityTooLarge.md)
* [primitive StatusRequestURITooLong](net-http-StatusRequestURITooLong.md)
* [primitive StatusUnsupportedMediaType](net-http-StatusUnsupportedMediaType.md)
* [primitive StatusRequestedRangeNotSatisfiable](net-http-StatusRequestedRangeNotSatisfiable.md)
* [primitive StatusExpectationFailed](net-http-StatusExpectationFailed.md)
* [primitive StatusTeapot](net-http-StatusTeapot.md)
* [primitive StatusPreconditionRequired](net-http-StatusPreconditionRequired.md)
* [primitive StatusTooManyRequests](net-http-StatusTooManyRequests.md)
* [primitive StatusRequestHeaderFieldsTooLarge](net-http-StatusRequestHeaderFieldsTooLarge.md)
* [primitive StatusUnavailableForLegalReasons](net-http-StatusUnavailableForLegalReasons.md)
* [primitive StatusInternalServerError](net-http-StatusInternalServerError.md)
* [primitive StatusNotImplemented](net-http-StatusNotImplemented.md)
* [primitive StatusBadGateway](net-http-StatusBadGateway.md)
* [primitive StatusServiceUnavailable](net-http-StatusServiceUnavailable.md)
* [primitive StatusGatewayTimeout](net-http-StatusGatewayTimeout.md)
* [primitive StatusHTTPVersionNotSupported](net-http-StatusHTTPVersionNotSupported.md)
* [primitive StatusNetworkAuthenticationRequired](net-http-StatusNetworkAuthenticationRequired.md)
* [interface Logger](net-http-Logger.md)
* [interface ServerNotify](net-http-ServerNotify.md)
* [actor HTTPServer](net-http-HTTPServer.md)
* [primitive ChunkedTransfer](net-http-ChunkedTransfer.md)
* [primitive StreamTransfer](net-http-StreamTransfer.md)
* [primitive OneshotTransfer](net-http-OneshotTransfer.md)
* [type TransferMode](net-http-TransferMode.md)
* [class Payload](net-http-Payload.md)
* [primitive MimeTypes](net-http-MimeTypes.md)
* [interface HTTPSession](net-http-HTTPSession.md)
* [interface HTTPHandler](net-http-HTTPHandler.md)
* [interface HandlerFactory](net-http-HandlerFactory.md)
* [primitive DiscardLog](net-http-DiscardLog.md)
* [class ContentsLog](net-http-ContentsLog.md)
* [class CommonLog](net-http-CommonLog.md)
* [class HTTPClient](net-http-HTTPClient.md)


## Private Types

* [class _SessionGuard](net-http-_SessionGuard.md)
* [class _HTTPConnTestHandler](net-http-_HTTPConnTestHandler.md)
* [class _HTTPConnTestHandlerFactory](net-http-_HTTPConnTestHandlerFactory.md)
* [primitive _FixedResponseHTTPServerNotify](net-http-_FixedResponseHTTPServerNotify.md)
* [class _ServerListener](net-http-_ServerListener.md)
* [actor _ServerConnection](net-http-_ServerConnection.md)
* [class _ServerConnHandler](net-http-_ServerConnHandler.md)
* [primitive _ExpectRequest](net-http-_ExpectRequest.md)
* [primitive _ExpectResponse](net-http-_ExpectResponse.md)
* [primitive _ExpectHeaders](net-http-_ExpectHeaders.md)
* [primitive _ExpectContentLength](net-http-_ExpectContentLength.md)
* [primitive _ExpectChunkStart](net-http-_ExpectChunkStart.md)
* [primitive _ExpectChunk](net-http-_ExpectChunk.md)
* [primitive _ExpectChunkEnd](net-http-_ExpectChunkEnd.md)
* [primitive _ExpectBody](net-http-_ExpectBody.md)
* [primitive _ExpectReady](net-http-_ExpectReady.md)
* [primitive _ExpectError](net-http-_ExpectError.md)
* [type _PayloadState](net-http-_PayloadState.md)
* [class _HTTPParser](net-http-_HTTPParser.md)
* [class _HostService](net-http-_HostService.md)
* [primitive _ConnConnecting](net-http-_ConnConnecting.md)
* [actor _ClientConnection](net-http-_ClientConnection.md)
* [class _ClientConnHandler](net-http-_ClientConnHandler.md)
