xps2image
=========

Convert xps documents to a .NET bitmap

Installing via Nuget
====================

	Install-Package xps2img

Usage
=====

[Additional examples](https://github.com/peters/xps2image/blob/master/src/xps2img.tests/Xps2ImageTests.cs)

**Convert a xps document to png from disk**

```cs
using (var xpsConverter = new Xps2Image("multipage.xps"))
{
	var images = xpsConverter.ToBitmap(new Parameters
	{
		ImageType = ImageType.Png,
		Dpi = 300,
		ImageOptions = new ImageOptions(100, TiffCompressOption.Zip),                    
	});

	Debugger.Break();
}
```

**Convert a xps document to png from a byte array**

```cs
using (var xpsConverter = new Xps2Image(File.ReadAllBytes("multipage.xps")))
{
	var images = xpsConverter.ToBitmap(new Parameters
	{
		ImageType = ImageType.Png,
		Dpi = 300,
		ImageOptions = new ImageOptions(100, TiffCompressOption.Zip),                    
	});

	Debugger.Break();
}
```

**Convert a xps document to png from stream**

```cs
using (var xpsConverter = new Xps2Image(new MemoryStream(File.ReadAllBytes("multipage.xps"))))
{
	var images = xpsConverter.ToBitmap(new Parameters
	{
		ImageType = ImageType.Png,
		Dpi = 300,
		ImageOptions = new ImageOptions(100, TiffCompressOption.Zip),                    
	});

	Debugger.Break();
}
```
