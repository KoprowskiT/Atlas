

# Atlas

[![Build Status]][Build Latest]

![Atlas Logo]

----

Atlas is a tool for automating the deployment, configuration, and maintenance of DevOps engineering systems. 
It can be run interactively from the command line, or can be run entirely unattended as part of a VSTS build or release defintion. 
An Atlas workflow revolves around making the appropriate REST API calls to [VSTS][VSTS REST API], [Active Directory][Azure AD REST API], and [Azure Resource Manager][Azure RM REST API]. 

There is a REST API for everything. 
With Atlas you can make the configuration of everything from CI/CD to production servers consistent, reproducable, and reviewable by capturing them as source controlled templates.

----

## Features

* [YAML] or [JSON] syntax to define workflows and input parameters

* [Handlebars] template engine enables workflows to be highly flexible

* [JMESPath] provides query language for inputs, outputs, and data transformations

* Works cross-platform as a .NET Core executable

* Invokes any [Azure RM][Azure RM REST API], [Azure AD][Azure AD REST API], or [VSTS][VSTS REST API] REST API 

* From the command line, REST API calls are secured via interactive Active Directory login, similar to `az login`

* From a VSTS build or release definition, REST API calls are secured via [VSTS service connection to Azure](https://docs.microsoft.com/en-us/vsts/pipelines/library/service-endpoints?view=vsts)

* Renders output values and additional templated files to a target folder

* Operations support conditional executions, retries and looping, and can throwing detailed exceptions

* Extensively detailed log output and safe `--dry-run` support simplify troubleshooting

* Values which are declared secret are redacted (replaced with xxxx) when written to console output and log files

## Limitations

* Does not allow arbitrary code or command-line execution in order to limit what can be done to the machine executing a workflow

* Currently designed for Active Directory authentication for Azure and VSTS resources

* Not yet available as a class library package

## Goals

* Packing workflows into zip or tarball archive files, publishing and executing workflows from feed locations

* Establishing a repository for collaboration on common in-progress and stable workflows, and default location for common workflows

* Shared workflows for larger scenarios, e.g. ASP.NET Core services on Kubernetes with VSTS CI/CD, Azure VM clusters, Azure DNS, ATM, and ALB for geo-redundant load balancing and service routing

----

## Contributing

This project welcomes contributions and suggestions. Most contributions require you to
agree to a Contributor License Agreement (CLA) declaring that you have the right to,
and actually do, grant us the rights to use your contribution. For details, visit
https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need
to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the
instructions provided by the bot. You will only need to do this once across all repositories using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Reporting Security Issues

Security issues and bugs should be reported privately, via email, to the Microsoft Security
Response Center (MSRC) at [secure@microsoft.com](mailto:secure@microsoft.com). You should
receive a response within 24 hours. If for some reason you do not, please follow up via
email to ensure we received your original message. Further information, including the
[MSRC PGP](https://technet.microsoft.com/en-us/security/dn606155) key, can be found in
the [Security TechCenter](https://technet.microsoft.com/en-us/security/default).

[Atlas Logo]: https://github.com/Microsoft/Atlas/raw/master/docs/icon-128.png
[Handlebars]: http://handlebarsjs.com/
[YAML]: http://yaml.org/
[JSON]: http://json.org/
[JMESPath]: http://jmespath.org/
[Build Status]: https://msasg.visualstudio.com/Falcon/_apis/build/status/Atlas-CI?branch=master
[Build Latest]: https://msasg.visualstudio.com/Falcon/_build/latest?definitionId=6598&branch=master
[Azure RM REST API]: https://docs.microsoft.com/en-us/rest/api/azure/
[Azure AD REST API]: https://docs.microsoft.com/en-us/rest/api/graphrbac/
[VSTS REST API]: https://docs.microsoft.com/en-us/rest/api/vsts/?view=vsts-rest-5.0