# RT-EVM-JS 🔬

Real-time implementation in JavaScript of the **Eulerian Video Magnification** algorithm

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OpenCV.js](https://img.shields.io/badge/OpenCV.js-4.5.2-blue.svg)](https://docs.opencv.org/4.5.2/opencv.js)

## 📖 About

This project implements the **motion amplification** component of the Eulerian Video Magnification technique in pure JavaScript using OpenCV.js, allowing real-time amplification of subtle movements in video streams directly in the browser.

Based on the groundbreaking research paper ["Eulerian Video Magnification for Revealing Subtle Changes in the World"](https://people.csail.mit.edu/mrub/evm/) by MIT CSAIL, this implementation enables visualization of imperceptible motion phenomena such as:

- 🫁 **Breathing patterns** via chest movement amplification
- 🔬 **Micro-movements** in static structures (buildings, bridges)
- 🎵 **Vibrations** in objects caused by sound or mechanical forces
- 🏃 **Subtle body movements** and tremors

> **Note**: This implementation currently focuses on **motion magnification** only. Color amplification (e.g., for heart rate detection through skin color changes) is not yet implemented but may be added in future versions.

### How It Works

The Eulerian Video Magnification algorithm works by:

1. **Spatial Decomposition**: Building a Gaussian pyramid to decompose each video frame into different spatial frequency bands
2. **Temporal Filtering**: Applying bandpass filters to isolate specific frequency ranges over time
3. **Signal Amplification**: Multiplying the filtered temporal signals by an amplification factor (alpha)
4. **Reconstruction**: Combining the amplified signals with the original frame to reveal hidden motions

Unlike Lagrangian methods that track individual pixels, the Eulerian approach analyzes temporal variations at fixed spatial locations, making it computationally efficient for real-time processing.

## ✨ Features

- 🎥 **Real-time webcam processing** with front/back camera switching
- 📹 **Video file upload** support with looping playback
- 🎛️ **Adjustable parameters**:
  - Amplification factor (alpha)
  - Frequency range (Hz)
  - Pyramid levels
  - Temporal buffer size
  - Exposure control
  - Blur and noise attenuation
- 📊 **Performance monitoring**: FPS, processing time, buffer status
- 🎯 **Preset configurations** for common use cases (heart rate, breathing, motion)
- 🔴 **Video recording** of magnified output
- 💾 **Download processed videos** in WebM format
- 📱 **Responsive design** for desktop and mobile devices
- 🔒 **Privacy-focused**: All processing happens client-side, no data sent to servers

## 🚀 Installation & Usage

### Requirements

- A modern web browser with WebRTC support (Chrome, Firefox, Safari, Edge)
- Internet connection (to load OpenCV.js library from CDN)
- Webcam access or a video file to process

### Quick Start

1. **Clone the repository**:
   ```bash
   git clone https://github.com/MrMoDDoM/RT-EVM-JS.git
   cd RT-EVM-JS
   ```

2. **Serve the HTML file**:
   
   You can use any HTTP server. Here are some common options:

   **Option A: Python**
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   ```

   **Option B: Node.js (http-server)**
   ```bash
   npx http-server -p 8000
   ```

   **Option C: PHP**
   ```bash
   php -S localhost:8000
   ```

   **Option D: Just open the file**
   
   For testing purposes, you can simply open `rt-evm-js.html` directly in your browser (file:// protocol), though some browsers may restrict webcam access.

3. **Open in browser**:
   
   Navigate to `http://localhost:8000/rt-evm-js.html` (or the appropriate URL for your server)
4. **Start processing**:
   - Allow webcam access when prompted
   - Click "Avvia Elaborazione" (Start Processing) to begin
   - Adjust parameters in real-time using the sliders
   - Try preset configurations for specific use cases

### Tips for Best Results

- **Good lighting**: Ensure adequate, stable lighting for better signal detection
- **Stability**: Keep the camera steady (use a tripod if possible)
- **Distance**: Position yourself appropriately for the feature you want to detect
- **Frequency ranges**: Adjust based on the motion you want to amplify:
  - Breathing: 0.2 - 0.5 Hz (12-30 breaths/min)
  - Vibrations: 1.0 - 5.0 Hz
  - General motion: 0.5 - 3.0 Hz
- **Buffer length**: Longer buffers (30+ frames) provide more accurate filtering but increase latency
- **Motion detection**: Works best with subtle, periodic movements rather than large or rapid motions


## 📚 References

This project is based on the following research:

**Wu, H.-Y., Rubinstein, M., Shih, E., Guttag, J., Durand, F., & Freeman, W. T. (2012).**  
*Eulerian Video Magnification for Revealing Subtle Changes in the World.*  
ACM Transactions on Graphics (Proceedings SIGGRAPH 2012), 31(4).

- [Original Paper (PDF)](http://people.csail.mit.edu/mrub/papers/vidmag.pdf)
- [Project Page](https://people.csail.mit.edu/mrub/evm/)
- [MIT CSAIL](https://www.csail.mit.edu/)

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2026 Daniele Barattieri di San Pietro

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 👤 Author

**MrMoDDoM**

- Website: [https://mrmoddom.github.io/](https://mrmoddom.github.io/)
- GitHub: [@MrMoDDoM](https://github.com/MrMoDDoM)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/MrMoDDoM/RT-EVM-JS/issues).

## ⭐ Show Your Support

If you find this project useful, please consider giving it a star on GitHub!

## 🔮 Future Improvements

Potential enhancements for future versions:

- [ ] **Color amplification mode** for detecting subtle color changes (e.g., heart rate via skin color)
- [ ] Automatic parameter tuning based on input video analysis
- [ ] Improved UI/UX design
- [ ] Automatic ROI selection for frequency identification

---

**Note**: This is an educational/research implementation focused on **motion amplification**. Color amplification features (e.g., for heart rate detection) are not yet implemented. For medical or critical applications, please use validated professional equipment.
