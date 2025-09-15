# 🎮 Input Device Tester

A complete web-based testing solution for gamepads, keyboards, and mice with functionality similar to gpadtester.com. Test all your input devices directly in your browser without any software installation.

## ✨ Features

### 🎮 Gamepad Testing
#### 🔌 Controller Detection
- Auto-detect gamepad connections (USB/Bluetooth)
- Support for multiple controller types (Xbox, PlayStation, Generic)
- Real-time connection status monitoring
- Controller information display

#### 🔘 Button Testing
- Real-time button press visualization
- Pressure sensitivity testing for analog buttons
- Button response time measurement
- Visual feedback with animations

#### 🕹️ Analog Stick Testing
- Real-time stick position visualization
- Stick drift detection and measurement
- Dead zone testing
- Calibration verification
- Visual drift alerts

#### 🎯 Trigger Testing
- Analog trigger pressure testing
- Full range testing (0-100%)
- Real-time pressure bars
- Sensitivity analysis

#### 📳 Vibration Testing
- Light vibration testing
- Strong vibration testing
- Custom vibration patterns
- Haptic feedback verification

### ⌨️ Keyboard Testing
#### 🔤 Visual Keyboard Layout
- Full QWERTY keyboard visualization
- Real-time key press highlighting
- Function keys and special keys support
- Modifier keys (Ctrl, Alt, Shift, Win) indication

#### 📝 Typing Performance
- Real-time typing test with WPM calculation
- Key press counting and statistics
- Last key pressed indicator
- Words per minute tracking

#### 🔧 Special Keys Testing
- Arrow keys visualization
- Modifier key combinations
- Function key responsiveness
- Key code detection and display

### 🖱️ Mouse Testing
#### 🎯 Movement Tracking
- Real-time mouse position tracking
- Mouse speed calculation
- Visual crosshair following cursor
- Mouse trail effects

#### 🔘 Button Testing
- Left, right, and middle click detection
- Click counting for each button
- Visual feedback on button presses
- Real-time click statistics

#### 🎡 Scroll Wheel Testing
- Scroll direction detection (up/down)
- Scroll amount measurement
- Scroll event logging with timestamps
- Real-time scroll feedback

#### 👆 Advanced Mouse Features
- Double-click detection and counting
- Drag and drop functionality testing
- Mouse precision and accuracy tests
- Advanced gesture recognition

### 🔍 Universal Diagnostics
- Automatic issue detection for all devices
- Device-specific troubleshooting recommendations
- Real-time diagnostic status updates
- Performance metrics and analysis

### 🛠️ Troubleshooting Guide
- Built-in repair recommendations
- Device-specific solutions
- Driver and firmware update guidance
- Common issue fixes

## 🚀 Quick Start

1. **Clone or download** this repository
2. **Open** `index.html` in a modern web browser
3. **Select a device tab**: Gamepad, Keyboard, or Mouse
4. **Start testing**:
   - **Gamepad**: Connect via USB/Bluetooth and press any button
   - **Keyboard**: Start typing or press keys to test
   - **Mouse**: Move, click, scroll, and drag to test functionality

## 💻 Browser Support

- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Edge
- ✅ Safari (limited vibration support)
- ❌ Internet Explorer (not supported)

## 🎮 Supported Controllers

- **Xbox Controllers**: Xbox One, Xbox Series X/S, Xbox 360
- **PlayStation Controllers**: PS5 DualSense, PS4 DualShock, PS3
- **Generic Controllers**: Most USB/Bluetooth gamepads
- **Nintendo Controllers**: Pro Controller, Joy-Cons (limited support)

## 🔧 Technical Implementation

### Core Technology Stack
- **HTML5 Gamepad API** for controller interfacing
- **Vanilla JavaScript** for functionality
- **CSS3** with animations for visual feedback
- **Responsive design** for all screen sizes

### Key Components
- **GamepadTester Class**: Main controller logic
- **Real-time polling**: 60fps input monitoring
- **Event handling**: Connection/disconnection events
- **Visual feedback**: Instant UI updates
- **Diagnostic algorithms**: Issue detection logic

### API Usage
```javascript
// Detect gamepad connections
window.addEventListener('gamepadconnected', (event) => {
    console.log('Gamepad connected:', event.gamepad);
});

// Poll gamepad state
function gameLoop() {
    const gamepads = navigator.getGamepads();
    // Process gamepad inputs
    requestAnimationFrame(gameLoop);
}
```

## 📁 File Structure

```
gamepad-tester/
├── index.html          # Main HTML structure
├── styles.css          # Complete styling and animations
├── gamepad-tester.js   # Core JavaScript functionality
└── README.md           # This documentation
```

## 🔍 How It Works

1. **Detection**: Uses `gamepadconnected` events to detect controllers
2. **Polling**: Continuously monitors gamepad state at 60fps
3. **Processing**: Analyzes button presses, stick movements, and trigger pressure
4. **Feedback**: Updates UI in real-time with visual indicators
5. **Diagnostics**: Runs algorithms to detect common issues
6. **Vibration**: Tests haptic feedback using Vibration API

## 🛠️ Advanced Features

### Stick Drift Detection
```javascript
detectStickDrift(stick, x, y) {
    const magnitude = Math.sqrt(x * x + y * y);
    if (magnitude > this.driftThreshold) {
        // Drift detected logic
    }
}
```

### Vibration Testing
```javascript
async testVibration(type) {
    await gamepad.vibrationActuator.playEffect('dual-rumble', {
        startDelay: 0,
        duration: 500,
        weakMagnitude: 0.5,
        strongMagnitude: 0.8
    });
}
```

### Real-time Diagnostics
- **Drift Analysis**: Monitors stick movement over time
- **Button Health**: Tracks button press frequency and response
- **Trigger Range**: Validates full trigger travel
- **Connection Stability**: Monitors connection status

## 🎨 Customization

### Styling
Modify `styles.css` to customize:
- Color schemes
- Animation effects
- Layout responsiveness
- Visual feedback intensity

### Functionality
Extend `gamepad-tester.js` to add:
- Additional controller mappings
- Custom diagnostic algorithms
- Extended vibration patterns
- New testing modes

## 🐛 Troubleshooting

### Common Issues

1. **Controller not detected**
   - Ensure controller is properly connected
   - Try pressing buttons to trigger detection
   - Check browser compatibility

2. **Buttons not responding**
   - Verify controller is working in other applications
   - Try reconnecting the controller
   - Update controller drivers

3. **Vibration not working**
   - Check if controller supports vibration
   - Ensure browser supports Vibration API
   - Verify controller settings

### Browser-Specific Notes

- **Chrome**: Full support for all features
- **Firefox**: Good support, some vibration limitations
- **Safari**: Limited vibration support on some devices
- **Mobile browsers**: Limited gamepad support

## 📱 Mobile Support

While primarily designed for desktop use, the interface is responsive and works on mobile devices for demonstration purposes. Note that mobile gamepad support varies by browser and device.

## 🔒 Privacy & Security

- **No data collection**: All testing happens locally in your browser
- **No external requests**: Completely offline functionality
- **No installation required**: Pure web-based solution
- **Open source**: Full transparency of code

## 🤝 Contributing

Feel free to contribute improvements:
1. Fork the repository
2. Make your changes
3. Test thoroughly
4. Submit a pull request

## 📄 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

- Inspired by gpadtester.com
- Built using the HTML5 Gamepad API
- Modern web standards for cross-platform compatibility

---

**Ready to test your gamepad?** Open `index.html` and connect your controller! 🎮
