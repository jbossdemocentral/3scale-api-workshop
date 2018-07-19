# Red Hat API Integration &amp; Management Workshop

This is a subset of labs from the Red Hat API Integration &amp; Management Workshop. This workshop will guide you on your journey to create your first API managed by Red Hat 3scale API Management. We loosely base it on a very basic POC we would normally roll out.

The workshop is intended to be delivered in person, but will provide enough guidance for self-paced consumption.

## Introduction

### Products and Projects

* [Red Hat OpenShift Container Platform](https://www.redhat.com/en/technologies/cloud-computing/openshift)
* [Red Hat 3scale API Management](https://www.redhat.com/en/technologies/jboss-middleware/3scale)
* [Red Hat Fuse](https://access.redhat.com/products/red-hat-fuse)
* [Red Hat Single Sign On](https://access.redhat.com/products/red-hat-single-sign-on)
* [Apicurio](https://www.apicur.io/)
* [Microcks](http://microcks.github.io/)

### Pre-requisites

* Knowledge of the current version of the OpenAPI specification: [OpenAPI Specification 3.0.1](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.1.md)
* Internet access with no blacklist filtering on:
  * *.openshiftworkshop.com
  * *.onlinecurl.com

### Agenda

A rough agenda for the workshop looks like this:

* Red Hat 3scale API Management Overview: 20 mins
* Workshop Overview: 10 mins
* Labs: 3hrs

### Slides

Check the latest [Slides](https://docs.google.com/presentation/d/1nizTZlzuO7AqQkEHr1OxDoIW2Wew7Gxe2a93sPqfiQE/edit?usp=sharing) for delivering this workshop.

### Labs

Session 1: API Design, Deployment and Management

* [01. API Design](docs/labs/lab01/#lab-1) - Create an OpenAPI Specification-based Contract
* [02. API Deployment](docs/labs/lab02/#lab-2) - Deploying APIs to OpenShift
* [03. API Management](docs/labs/lab03/#lab-3) - Take Control of APIs

Session 2: API Security and Usage

* [04. API Security](docs/labs/lab04/#lab-4) - Securing APIs with OpenID Connect and Red Hat Single Sign On
* [05. API Developers](docs/labs/lab05/#lab-5) - Discovering APIs from Developer Portal
* [06. API Consumption](docs/labs/lab06/#lab-6) - Connect Applications and APIs

### Optional Labs

* [A. API Mocking](docs/labs/lab102/#lab-102) - Bring your APIs to Life

We recommend you to begin your journey with the first lab [API Design - Create an OpenAPI Specification-based Contract](docs/labs/lab01/#lab-1)

### Installation

If you feel comfortable, you can setup your own environment to host the software required in the labs. Follow the [install instructions](docs/install.md) to install and configure the environment.

### FAQ

### Support & Ownership

GitHub Repo: [https://github.com/hguerrero/3scale-api-workshop](https://github.com/hguerrero/3scale-api-workshop)

Feel free to ask [Hugo Guerrero](mailto:hguerrero@redhat.com) if you need some support when there are any questions left or if you need some support.

### Contributing

We welcome all forms of contribution (content, issues/bugs, feedback). Please see the [Contribution Guidelines](docs/contributing.md) for ways to help
