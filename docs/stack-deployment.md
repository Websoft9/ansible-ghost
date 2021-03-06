# Deployment

**Deployment is to copy the pre-installed Ghost package online to your Cloud Server**. For example, after the user subscribes Ghost on the Cloud Platform, the Platform will automatically copy the Ghost to the corresponding Cloud Server.

- If you have deployed the Ghost, go to [Initial Installation](/stack-installation.md) to complete the operation.
- If not, first you need to deploy Ghost to your cloud server .

We offer two schemes for Ghost deployment and the results are the same. The process of deployment is automatic, please wait patiently.

## Deploy by Image

**To deploy by Image** means to start instance based on Ghost images, so as to obtain the same system environment as the image contains. **Ghost Image** provides OS and software environment needed.

For users with experience with cloud servers, to deploy by Image means "one-click deployment".

Websoft9 publishes [Ghost image](https://apps.websoft9.com/ghost) on Cloud Platforms and there are three methods to deploy it. 

* When **create New Instance**, you can select the Ghost image as the system boot template.
* When you **subscribe Ghost** at Marketplace, the system will ask you to create a new instance for this image in the meantime.
* When **re-install OS** for you instance, you can replace the existing image with a Ghost image.

## Deploy by Script

**To deploy by Script** means to run a script on your cloud instance to pull the pre-installed package online to your instance and configure it at the same time.

Websoft9 provides the [Ghost ansible automation script](https://github.com/Websoft9/ansible-ghost) on GitHub. If you are familiar with Ansible, you can deploy the Ghost to the instance automatically.

## Comparison

No matter you **deploy by image** or **deploy by script**, the results are the same. So, what is the difference between the two deployment methods?

Suggest to read the document [Deploy by Image vs Deploy by Script](https://support.websoft9.com/docs/faq/bz-product.html#deployment-comparison)