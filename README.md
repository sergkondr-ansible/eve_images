# eve_images
Upload images to your [Eve-NG](https://www.eve-ng.net/) network emulator

### Images preparing
At first you should to get all images you want to run on Eve. Then the images should be stored somewhere in the Internet where they can be download via direct link. I'm using AWS S3 for it. Also you have to split your images by folders, where folder name will be equal to the version of the image, for example: `mikrotik-6.46.1/hda.qcow2`

### IOL images
IOL images also supported by this role, but you need to put keygen to `files/iol.py`. And please pay the attention: you have to modify this script to print only licesne key information. This print should be the only print:
```python
print("[license]\n" + hostname + " = " + iouLicense + ";")
```

### Example
```yaml
eve_default_url_s3: "https://s3.eu-west-1.amazonaws.com/bucket.name"

eve_images_iol:
- "iol/L2-ADVENTERPRISEK9-M-15.2-IRON-20151103.bin"
- "iol/L3-ADVENTERPRISEK9-M-15.4-2T.bin"

eve_images_qemu:
- "mikrotik-6.46.1"
```
