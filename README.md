# Swift Coding Style
## Description
Provides a few general coding style suggestions for the Swift language. Updated for Swift 3.0. 

## Access Control
Keep public, private, etc. elements of a type grouped together. With higher access elements on top and others at the bottom, i.e. Public first and Private last.

**Example:**
```swift
class ImageViewerController: UIViewController, UIScrollViewDelegate {
    
    //MARK: - Public Section -
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
    
    //MARK: - Private Section -
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


## Naming Conventions

### When naming types avoid too generic suffixes like Controller or Manager
In iOS in particular the Controller suffix is easy to confuse with the pervasive \*ViewController name. Try to choose a more specific suffix for the role of the type you are defining.



## References
* [Apple's API Design Guidelines](https://swift.org/documentation/api-design-guidelines/)
* [Raywenderlich Swift Style Guide](https://github.com/raywenderlich/swift-style-guide)

