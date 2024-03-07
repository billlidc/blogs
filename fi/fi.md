# Google Fi Cellular Data Troubleshooting

### Problem

When in Canada, Google Fi cellular data under *Simply Unlimited* plan shows up “**No Service**”.

### References

* [Send and receive text messages (SMS & MMS)](https://support.google.com/fi/answer/6205096?hl=en&co=GENIE.Platform%3DiOS)

### Solution

#### Cellular Data

* **APN**: `h2g2`
* **Username**: leave blank
* **Password**: leave blank

#### LTE Setup (Optional)

* **APN**: `h2g2`
* **Username**: leave blank
* **Password**: leave blank

#### MMS

* **APN**: `h2g2`
* **Username**: leave blank
* **Password**: leave blank
* **MMSC**: [`http://m.fi.goog/mms/wapenc`](http://m.fi.goog/mms/wapenc)
* **MMS Proxy**: leave blank
* **MMS Max Message Size**: `23456789`
* **MMS UA Prof URL**: leave blank

#### Personal Hotspot

* **APN**: `h2g2-t`


### Screenshots
![Cellular Data Network](./cellular-data-network.jpg)