# Grafana DigitalOcean Marketplace Image Packer Build 

This repo contains the [Packer](https://www.packer.io/) files for the 
DO marketplace Grafana image. By integrating with the DigitalOcean API, the
initial Droplet creation, provisioning, and snapshoting can be done with a
single command:

    packer build grafana-marketplace.json

A DigitalOcean API token should be set using the `DO_API_TOKEN`
environment variable. This can be overridden at run time if necessary:

    packer build -var 'do_api_token=asecrectandsecureapitoken' grafana-marketplace.json

The name of the resulting snapshot will be `grafana-v{{version}}-{{timestamp}}`

**Note:** The image validation script has been copied here from [digitalocean/marketplace-partners](https://github.com/digitalocean/marketplace-partners).
That repository is its canonical source. Make sure you are using the latest
version from that repository.
