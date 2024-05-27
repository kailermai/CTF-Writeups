# Challenge Name: <Find a bag of money>

- Category: OSINT
- Points: <250>
- Solves: <>

## Challenge Description

Find the money sack, which is hidden in a landmark.

Flag format : CDDC24{   }
All letters are in lowercase.
Substitute spaces with _ (underscore).
e.g.) If the landmark is Gardens By the Bay, the flag to submit is CDDC24{gardens_by_the_bay}

## File Content

- Find+a+bag+of+money.zip (contains a text file)

`bafybeicjfojuswk3uzb54f76qxmwcfkf7tpf3lxg6u36mazkjk5a2gtybq`

## Solution

The string bafybeicjfojuswk3uzb54f76qxmwcfkf7tpf3lxg6u36mazkjk5a2gtybq is a Content Identifier (CID) used in the InterPlanetary File System (IPFS). IPFS is a decentralized file storage system that allows users to store and share files across a distributed network.

### Understanding IPFS and CIDs

#### IPFS (InterPlanetary File System):

- A protocol and peer-to-peer network designed to create a permanent and decentralized method of storing and sharing files.
- Uses content-addressing to uniquely identify each file in a global namespace connecting all computing devices.

#### CID (Content Identifier):

- A unique identifier for a piece of content on the IPFS network.
- CIDs are generated based on the content itself, meaning that even a small change in the content will result in a completely different CID.
- Ensures that the data referenced by the CID is immutable and verifiable.

---

To access the CID, we can use:

`https://ipfs.io/ipfs/bafybeicjfojuswk3uzb54f76qxmwcfkf7tpf3lxg6u36mazkjk5a2gtybq`

This will download a zip file containing 1000 images of money bags. Inspecting the metadata of the images, we can see that each picture maps to a different location on the map. Hence, we can use exiftools to extract the longitude and latitude of each image into a CSV file:

`./exiftool -csv -gpslongitude -gpslatitude > test1.csv (location of the folder, eg: /Desktop/download)`

The flags -csv outputs a csv file withgpslongitude and gpslatitude, with the name test1.csv.

![Screenshot of the challenge](/Images/CDDC2024_Qualifiers/Qualifier_OSINT_moneybag1.png)

With this csv file, we can use a gps visualiser to plot the points of these gps locations on a map. I used gpsvisualiser for this. Importing the csv file gets this:

![Screenshot of the challenge](/Images/CDDC2024_Qualifiers/Qualifier_OSINT_moneybag2.png)

We can see that there is an anomaly in the points plotted. Zooming in on it gets us the location of the money bag, Taj Mahal.

## Flag

CDDC24{taj_mahal}

## Notes

NIL

---

[Back to home](https://github.com/kailermai/CTF-Writeups/tree/main/CDDC2024)
