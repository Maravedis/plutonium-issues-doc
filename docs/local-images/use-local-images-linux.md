Disclaimer: English is not my first language, apologies for any mistake.

# Migrate to using local images in plutonium (FoundryVTT)

## Why?

By default, the plutonium importer points to the images on the 5eT website, as to not burden your installation with gigabytes of pictures.

But with 5e tools broken, you now have broken images everywhere in your scenes. Not fancy, and bothersome.

Using local images is less easy than setting up the mirrors. It also takes a significant amount of space on your drive. Be certain it's what you want to do.


## I. Cover your ass

**BACK UP YOUR WORLD**. This is really easy to do. You should do it. Always. Here is an example on how to do it with `tar`:
```bash
$ cd $FOUNDRY_DATA_FOLDER/Data/worlds
$ tar -cf your-world.tar your-world
```
and just like that you have a tar archive of your world that you can reopen with `tar -xf your-world.tar`.

## II. Get the assets

Download the images [here](https://mega.nz/file/eWQm2LTD#ibOwrcY0DjvgGkEKkKvvZiCuRLmuFQph1TCw233RcmY). This is a BIG download (~3.6Gb).

## III. Install the assets

The images need to go into your plutonium module folder. But there is a caveat: module updates typically wipe the whole folder.
For this reason, we will be using symbolic links to store the image elsewhere and not have to do everything all over again when the next update rolls in.

Supposing the zipfile is in `~/Downloads`:
```bash
$ unzip 5eTools_img.1.134.0.zip # this will create a `tmp` file in Downloads
$ mv tmp/5et/img ~/Documents/5eImages # or wherever you want to put it
$ rm -rf tmp # remove the empty folder left
$ cd $FOUNDRY_DATA_FOLDER/Data/modules/plutonium
$ ln -s ~/Documents/5eImages img # Create the symbolic link. it's important the link is named 'img'
```
Now, even if you update plutonium, all you have to do is re-create the symbolic link in the module folder.

## IV. Configure Plutonium

You need to configure plutonium to use local images. Go to plutonium settings, `import` tab, and tick the `Use Local Images`.

Save and refresh your page.

## V. Fix the images of already present tokens

Surged20 did an excellent tool to update your tokens / actors image that you can find [here](https://github.com/surged20/foundryvtt-update-image-macro).

Just follow the instructions :).



