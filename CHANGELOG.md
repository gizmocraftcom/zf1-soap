# Changelog

## 3.0.0

- Package renamed to `gizmocraft/zendframework1-soap` (fork of `diablomedia/zendframework1-soap`).
- Requires PHP >= 8.5; CI runs on PHP 8.5 and 8.6.
- Depends on `gizmocraft/zendframework1-config` ^3.0.0, `-exception` ^2.0.0, `-server` ^2.0.0, `-uri` ^2.0.0 and `-xml` ^2.0.0.
- Dev dependencies upgraded to PHPUnit 13, PHPStan 2.3, php-cs-fixer 3.95 and GrumPHP 2.27; `composer-require-checker` dropped.
- Fixed: `Zend_Soap_Client::_doRequest()` called the callable `SoapClient::__doRequest`, which is deprecated since PHP 8.2 (`Callables of the form ["Zend_Soap_Client_Common", "SoapClient::__doRequest"] are deprecated`). It now calls the new `Zend_Soap_Client_Common::_doParentRequest()`.
- Added public method `Zend_Soap_Client_Common::_doParentRequest()` (internal; runs `SoapClient::__doRequest()`).
- Tests migrated to PHPUnit 13 attributes; added a test for the default `_doRequest()` path.
