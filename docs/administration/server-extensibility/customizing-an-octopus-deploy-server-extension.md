---
title: Customizing an Octopus Server extension
description: Octopus Deploy built-in server extensions are available on GitHub and can be forked and customized.
---

!include <server-extensibility-deprecated>

As part of the Octopus Deploy installation, a number of extensions are provided out-of-the-box.  All of these extensions are managed as open-source projects on GitHub.  They include:

- [UsernamePassword authentication](https://github.com/OctopusDeploy/UsernamePasswordAuthenticationProvider).
- [Active Directory authentication](https://github.com/OctopusDeploy/DirectoryServicesAuthenticationProvider).
- [Guest authentication](https://github.com/OctopusDeploy/GuestAuthenticationProvider).
- [OpenID Connect based authentication](https://github.com/OctopusDeploy/OpenIDConnectAuthenticationProviders) (e.g. Azure AD and GoogleApps).

One of the reasons behind open-sourcing these projects is to allow users to customize them if they need to.  For example, Active Directory configurations can vary dramatically and for some users it may make sense to modify parts of our implementation.

## Customizing the code {#CustomisinganOctopusDeployserverextension-Customisingthecode}

The simplest option for customizing the code is to fork the project in GitHub. This will allow you to keep up to date with any changes we might make and you'll be able to submit PRs.

## Building the code {#CustomisinganOctopusDeployserverextension-Buildingthecode}

Included in the project repositories are the [Cake](http://cakebuild.net/) build scripts we use to build the extensions.  These are used to both compile the dlls and produce the NuGet packages that we use for distribution.  To use a customized extension, you only need the compiled dll.

## Installing a custom extension {#CustomisinganOctopusDeployserverextension-&#39;Installing&#39;acustomextension}

Once you've compiled the dll, [installing it is as simple as putting it in the right folder](/docs/administration/server-extensibility/installing-a-custom-server-extension.md) and restarting the Octopus Server.
