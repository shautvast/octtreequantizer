Does quantization in pure rust on Rgba image, using https://crates.io/crates/image

algorithm:
https://observablehq.com/@tmcw/octree-color-quantization

inspired by to https://github.com/objectProfessionals/movieMaps

```
fn quantize_image() -> Result<(), ImageError> {
    let src: RgbaImage = image::open("some_image.jpg").unwrap().into_rgba8();
    let dest = quantize(&src, 256);
    dest.save_with_format("output.jpg", image::ImageFormat::Jpeg)?;
    Ok(())
}
```