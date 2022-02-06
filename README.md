# Hack the Future Website

A [Jekyll](https://jekyllrb.com/)-based website using the
[Minimal Mistakes Jekyll theme](https://github.com/mmistakes/minimal-mistakes)
for the [Hack the Future](https://htfpurdue.org) club at
[Purdue University](https://purdue.edu).

## Development

For detailed instructions on how to configure, customize, add/migrate content,
and more read the
[theme's documentation](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).

## Deployment

### Initial Setup

The site uses GitHub Actions to deploy the files on an
[AWS EC2](https://aws.amazon.com/ec2/) instance running
[Bitnami LAMP](https://bitnami.com/stack/lamp). The connection information (SSH
host, key, username, and port) should be set in the GitHub repository.

Additionally, the
[Bitnami Let's Encrypt tool](https://docs.bitnami.com/aws/how-to/generate-install-lets-encrypt-ssl/)
should be run prior to deploying the site for the first time.

The domain name should have a DNS "A" record that points to the Elastic IP set
in AWS ([see below](#aws-configuration)).

### Updates

After the server has been setup, deploying the site is as simple as running
`JEKYLL_ENV=production bundle exec jekyll build` to build the site (on your local machine) and pushing
the changes to the main branch on GitHub. This will trigger the workflow and
update the website.

### AWS Configuration

The app is hosted on an AWS EC2 t2.micro instance, with an
[Elastic IP](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html)
attached. If terminating the instance, remember to remove the Elastic IP to
avoid unnecessary charges.

### Removal

To remove the website, delete the DNS record and terminate the EC2 instance and
IP.

## License

Licensed under the terms of the [LICENSE](./LICENSE) file.
