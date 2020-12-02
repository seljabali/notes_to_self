### Extensions:
1. bitmap = Bitmap.fromFile(file, options)
2. bitmap = BitmapFactory.decodeFile(file, options)
3. bitmap = file.toBitmap(options)

#1 - If it is not that broadly used, as it will not polute File namespace.

#2 - When there are a lot of different factories.

#3 - If there is only one way to convert file to btimap and it is used quite broadly.
