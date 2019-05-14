# UIImage JPEGDecoding

To avoid `applejpeg_decode_image_all`. Basically it's automatically invoked when you do something like:
```swift
imageView.image = anImage
```

## Usage
Make sure your call this method in background thread to not block main thread. And cache it somewhere for later use.
```swift
DispatchQueue.global().async {
  let image = anImage.decoded()
}
```
