# Swift 3.0 Coding Style

## Description
Provides a few general coding style suggestions for the Swift language. Updated for Swift 3.0. 

## Access Control
Keep public, private, etc. elements of a type grouped together. With higher access elements on top and others at the bottom, i.e. Public first and Private last.

**Example:**
```swift
class ImageViewerController: UIViewController, UIScrollViewDelegate {
    
    //MARK: - PUBLIC SECTION -
    var image: UIImage? {
        //code
    }
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // code
    }
    
    override func viewDidLayoutSubviews() {
        super.viewDidLayoutSubviews()
        updateScrollViewZoomLevel()
    }
    
    //MARK: - PRIVATE SECTION -
    @IBOutlet private weak var scrollView: UIScrollView! {
        didSet {
            scrollView.contentSize = imageView.frame.size
            scrollView.delegate = self
        }
    }
    
    private var imageView = UIImageView()
    
    private func updateScrollViewZoomLevel() {
        //code
    }
}
```

## References
* [Apple's API Design Guidelines](https://swift.org/documentation/api-design-guidelines/)
* [Raywenderlich Swift Style Guide](https://github.com/raywenderlich/swift-style-guide)

