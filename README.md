# ionic-csharp-sdk
The Machina Tools SDK for C# provides an easy-to-use interface Windows developers to build client interfaces that interact with the Ionic Machina. This release contains significant changes to the underlying cryptography, a key feature of which is the ability to dynamically load the crypto module. Supporting a dynamically loaded crypto module offers several benefits including:

* The ability to use other third-party FIPS-compliant crypto modules
* Better application performance when initializing the Agent class
* Updating the crypto module independently of the core SDK code (allowing crypto module updates independently of Machina SDK releases).

By default the SDK loads a FIPS-validated version of the OpenSSL open source library. The SDK package also includes an additional platform-specific implementation crypto module that can be used instead of the OpenSSL FIPS implementation. This module is not FIPS validated, and is provided to work around cross-platform limitations including a limited sourced of entropy.

The 2.1 release includes the following crypto modules:

* libCryptoAbstractLibFips - A FIPS-validated version of the OpenSSL open source crypto module (default module)
* libCryptoAbstractLibPlatform - A non FIPS-validated version of the OpenSSL open source crypto module which uses OS specific, non-blocking RNG sources

See Machina Developers for more information.
