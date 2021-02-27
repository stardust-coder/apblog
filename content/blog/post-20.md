---
title: "カメラを背景画像に"
date: 2021-02-25
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories:
  - "programming"   

tags:
  - "swift"
  
  
# post type
type: "post"
---

## Version
Xcode12.4
Swift5.3.2

## めいいっぱいUIViewを作って、そこにカメラの映像を入力する

Main.storyboardでめいいっぱいのUIViewを作り、

8行目の@IBOutlet と接続する。

```Swift
class ViewController: UIViewController {
    
    
    var mySession : AVCaptureSession!
    var myDevice : AVCaptureDevice!
    var myImageOutput : AVCapturePhotoOutput!

    @IBOutlet weak var myView: UIView!

    override func viewDidLoad() {
        super.viewDidLoad()
        // セッションの作成
        mySession = AVCaptureSession()
        // カメラデバイスの取得
        if #available(iOS 10.0, *) {

            let discoverySession = AVCaptureDevice.DiscoverySession(deviceTypes: [AVCaptureDevice.DeviceType.builtInWideAngleCamera], mediaType: AVMediaType.video, position: .back)

            for device in discoverySession.devices {
                myDevice = device
            }
        } else {
          myDevice = AVCaptureDevice.default(for: .video)
        }
        myView.backgroundColor = UIColor.clear

        do {
          // バックカメラからVideoInputを取得
          let videoInput = try AVCaptureDeviceInput.init(device: myDevice)
          // セッションに追加
          mySession.addInput(videoInput)
          // 画像を表示するレイヤーを生成
          let myVideoLayer = AVCaptureVideoPreviewLayer(session: mySession)
          myVideoLayer.frame = myView.bounds
          myVideoLayer.videoGravity = AVLayerVideoGravity.resizeAspectFill

          // Viewに追加
          myView.layer.addSublayer(myVideoLayer)

          mySession.startRunning()
        } catch {
          return
        }
    }
    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
    override var shouldAutorotate: Bool {
        get {
          return false
        }
    }
}
```

結局使わなかったこの機能泣...