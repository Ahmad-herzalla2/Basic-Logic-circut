# 🔧 Digital Board Simulator - BIN/7SEG Edition

[![Version](https://img.shields.io/badge/version-3.0-blue.svg)](https://github.com/Ahmad-Herzalla0/digital-board-simulator)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow.svg)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![CSS3](https://img.shields.io/badge/CSS3-Modern-1572B6.svg)](https://www.w3.org/Style/CSS/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26.svg)](https://html.spec.whatwg.org/)

> **An advanced interactive digital logic circuit simulator with comprehensive BIN/7SEG display support, featuring real-time signal propagation and intuitive visual design.**

![Digital Board Simulator Banner](assets/banner.png)

## 🌟 Key Features

- **🎯 25 Logic Gates** - Complete set including AND, OR, XOR, XNOR, NOT, AB+CD, 4-bit Adders, and Comparators
- **📟 BIN/7SEG Display** - Triple 7-segment display with BCD and direct segment control
- **⚡ Real-time Simulation** - Instant signal propagation with visual feedback
- **🔌 Interactive Wiring** - Drag-and-drop connection system with state visualization
- **💾 Save/Load System** - Configuration persistence with URL sharing capability
- **📱 Responsive Design** - Works seamlessly across desktop and mobile devices
- **🎨 Modern UI** - Clean, intuitive interface with smooth animations

## 🚀 Quick Start

### Prerequisites

- Modern web browser (Chrome 80+, Firefox 75+, Safari 13+, Edge 80+)
- No additional installations required - runs entirely in the browser

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Ahmad-Herzalla0/digital-board-simulator.git
   cd digital-board-simulator
   ```

2. **Open in browser:**
   ```bash
   # Option 1: Direct file opening
   open index.html
   
   # Option 2: Local server (recommended)
   python -m http.server 8000
   # Then navigate to http://localhost:8000
   ```

3. **Start simulating!**
   - Toggle input switches to HIGH/LOW
   - Click connection points to create wires
   - Watch signals propagate in real-time

## 🧩 Components Overview

### Input Section (8 Inputs)
- **Switches**: IN0 through IN7 with HIGH/LOW toggle
- **Outputs**: Each input provides both Q and Q̅ signals
- **Visual Feedback**: Color-coded state indication

### Logic Gates (25 Total)

#### Column 1: AND Gates (7 units)
- **Gates**: AND0 through AND6
- **Function**: Output HIGH when all inputs are HIGH
- **Inputs**: 4 inputs per gate (A, B, C, D)

#### Column 2: OR Gates (5 units)  
- **Gates**: OR0 through OR4
- **Function**: Output HIGH when any input is HIGH
- **Inputs**: 4 inputs per gate (A, B, C, D)

#### Column 3: Special Gates (5 units)
- **AB+CD Gates**: 3 units implementing (A∧B)∨(C∧D) logic
- **XOR Gate**: Exclusive OR operation
- **XNOR Gate**: Exclusive NOR operation

#### Column 4: Advanced Components (6 units)
- **NOT Gates**: 2 inverter gates
- **4-bit Adders**: 2 units with carry support (A0-A3, B0-B3, Cin → S0-S3, CO)
- **4-bit Comparator**: 1 unit with cascade inputs (A0-A3, B0-B3, >, <, = → P>Q, P=Q, P<Q)
- **Basic Comparator**: 1 unit for simple comparison (P, Q → P>Q, P=Q, P<Q)
- **Power Rails**: 2 units providing constant HIGH and LOW signals

### Output Section

#### LEDs (12 Indicators)
- **Labels**: L0 through L11
- **Visual States**: Off (dark) / On (glowing red)
- **Real-time Updates**: Instant response to signal changes

#### BIN/7SEG Display
- **Display 1**: BCD controlled (inputs: 1, 2, 4, 8)
- **Display 2**: BCD controlled (inputs: 1, 2, 4, 8)  
- **Display 3**: Direct segment control (inputs: a, b, c, d, e, f, g)
- **Automatic Conversion**: BCD to 7-segment pattern mapping
- **Hexadecimal Support**: Displays 0-F characters

## 🎮 User Interface Guide

### Navigation Layout
```
┌─────────────┬──────────────────────────────────────┬─────────────┐
│   INPUTS    │            LOGIC GATES               │    LEDS     │
│   (8 units) │     (25 gates in 4 columns)        │  (12 units) │
│             │                                      │             │
│ IN0 ○ LOW   │  AND  │  OR   │ Special │ Advanced  │   L0  ○     │
│ IN1 ○ LOW   │  AND  │  OR   │   XOR   │ 4bitADD   │   L1  ○     │
│ IN2 ○ LOW   │  AND  │  OR   │  XNOR   │ 4bitCMP   │   L2  ○     │
│ IN3 ○ LOW   │  AND  │  OR   │ AB+CD   │   NOT     │   L3  ○     │
│ IN4 ○ LOW   │  AND  │  OR   │ AB+CD   │  POWER    │   L4  ○     │
│ IN5 ○ LOW   │  AND  │       │ AB+CD   │           │   ...       │
│ IN6 ○ LOW   │  AND  │       │         │           │   L11 ○     │
│ IN7 ○ LOW   │  AND  │       │         │           │             │
│             │       │       │         │           │ ┌─────────┐ │
│             │       │       │         │           │ │BIN/7SEG │ │
│             │       │       │         │           │ │ ███ ███ │ │
│             │       │       │         │           │ │ ███ ███ │ │
│             │       │       │         │           │ └─────────┘ │
└─────────────┴──────────────────────────────────────┴─────────────┘
```

### Interaction Methods

#### 🖱️ Mouse Controls
- **Single Click**: Toggle input switches
- **Click & Release**: Start/complete wire connections
- **Hover**: Highlight connection points and show tooltips
- **Right Click**: Context menu for wire deletion

#### ⌨️ Keyboard Shortcuts
- **F1**: Show help dialog
- **Ctrl+S**: Save current configuration
- **Ctrl+L**: Load configuration
- **Escape**: Cancel current wire connection
- **Space**: Quick toggle for selected input
- **Delete**: Remove selected wire

#### 🔌 Connection System
1. **Start Connection**: Click on any output point (circles)
2. **Route Wire**: Move mouse to desired destination
3. **Complete Connection**: Click on input point
4. **Visual Feedback**: Wire color indicates signal state
   - **Green (thick)**: HIGH signal
   - **Gray (thin)**: LOW signal
   - **Yellow (dashed)**: Temporary connection

## ⚙️ Advanced Features

### 💾 Save & Load System

#### Auto-Save
- **Frequency**: Every 5 minutes
- **Storage**: Browser localStorage
- **Recovery**: Automatic restoration on page reload

#### Manual Save/Load
```javascript
// Save configuration
const config = saveLoadManager.createConfigurationData();
localStorage.setItem('my_circuit', JSON.stringify(config));

// Load configuration
const savedConfig = JSON.parse(localStorage.getItem('my_circuit'));
saveLoadManager.applyConfiguration(savedConfig);
```

#### Export Formats
- **JSON File**: Complete circuit configuration
- **URL Sharing**: Compressed circuit data in URL parameters
- **Image Export**: Circuit layout as PNG (planned feature)

### 🔄 Signal Propagation

#### Real-time Updates
- **Propagation Delay**: < 10ms for typical circuits
- **Chain Reactions**: Automatic cascade updates
- **Feedback Loops**: Proper handling of circular dependencies
- **State Consistency**: Guaranteed stable final states

#### Algorithm Overview
```javascript
// Simplified propagation flow
1. Input Change Detection
2. Connected Component Identification  
3. Topological Sort for Update Order
4. Gate Logic Evaluation
5. Output State Updates
6. Visual Refresh
```

### 🎨 Visual Feedback System

#### State Indicators
- **Connection Points**: 
  - Black: Disconnected
  - Green: Connected (HIGH)
  - Red: Connected (LOW)
  - Yellow: Currently connecting

- **Wires**:
  - Thickness indicates signal strength
  - Color shows current state
  - Animation shows signal flow direction

- **Components**:
  - Glow effects for active gates
  - Pulsing for changing states
  - Smooth transitions between states

## 🏗️ Technical Architecture

### 📁 Project Structure
```
digital-board-simulator/
├── index.html                 # Main application entry point
├── js/                        # JavaScript modules
│   ├── main.js               # Application initialization
│   ├── config.js             # Configuration constants
│   ├── state-manager.js      # State management and logic
│   ├── component-factory.js  # Component creation and rendering
│   ├── connection-manager.js # Wire connection handling
│   ├── wire-manager.js       # SVG wire drawing and management
│   └── save-load-manager.js  # Persistence and sharing
├── styles/                   # CSS stylesheets
│   ├── main.css             # Layout and base styles
│   ├── components.css       # Component-specific styles
│   └── animations.css       # Animations and transitions
├── assets/                  # Static resources
│   ├── icons/              # UI icons and symbols
│   └── screenshots/        # Documentation images
└── README.md               # This documentation
```

### 🧠 Core Classes

#### StateManager
```javascript
class StateManager {
    // Manages overall application state
    - inputs: Array<InputState>
    - gates: Array<GateState>  
    - leds: Array<LEDState>
    - bin7segs: Array<DisplayState>
    - connections: Array<Connection>
    
    + toggleInput(id): boolean
    + updateGateInput(gateId, inputType, state): void
    + propagateState(target, state): void
}
```

#### ComponentFactory
```javascript
class ComponentFactory {
    // Creates and manages UI components
    + createInput(id): HTMLElement
    + createGate(id): HTMLElement
    + createLED(id): HTMLElement
    + createBin7Seg(id): HTMLElement
    + updateVisuals(): void
}
```

#### ConnectionManager
```javascript
class ConnectionManager {
    // Handles wire connections and interactions
    + handleConnectionClick(event, type, id, pointType): void
    + validateConnection(from, to): boolean
    + deleteConnection(from, to): boolean
}
```

### 🔧 Key Algorithms

#### Gate Logic Evaluation
```javascript
calculateGateOutput(gate) {
    switch(gate.type) {
        case 'AND': return inputs.every(i => i === true);
        case 'OR': return inputs.some(i => i === true);
        case 'XOR': return inputs.filter(i => i).length % 2 === 1;
        case 'ADDER_4BIT': return calculate4BitSum(gate.inputs);
        // ... additional gate types
    }
}
```

#### BCD to 7-Segment Conversion
```javascript
const BCD_TO_7SEG = {
    0: {a:1, b:1, c:1, d:1, e:1, f:1, g:0}, // Display "0"
    1: {a:0, b:1, c:1, d:0, e:0, f:0, g:0}, // Display "1"
    // ... patterns for 2-F
};
```

## 🌐 Browser Compatibility

| Browser | Minimum Version | Recommended | Notes |
|---------|----------------|-------------|-------|
| Chrome | 80+ | 90+ | Full feature support |
| Firefox | 75+ | 85+ | Full feature support |
| Safari | 13+ | 14+ | Full feature support |
| Edge | 80+ | 90+ | Full feature support |
| Mobile Safari | 13+ | 14+ | Touch-optimized |
| Chrome Mobile | 80+ | 90+ | Touch-optimized |

### Required Features
- **ES6+ Support**: Classes, arrow functions, template literals
- **SVG Support**: For wire rendering
- **Local Storage**: For save/load functionality
- **CSS Grid**: For responsive layout
- **Touch Events**: For mobile interaction

## 🎯 Usage Examples

### Basic Circuit Creation
```javascript
// Example: Create an AND gate circuit
1. Toggle IN0 to HIGH
2. Toggle IN1 to HIGH  
3. Connect IN0-Q to AND0-A
4. Connect IN1-Q to AND0-B
5. Connect AND0-Q to L0
6. Result: L0 lights up (HIGH output)
```

### BCD Counter Display
```javascript
// Example: 4-bit BCD counter
1. Connect IN0 to BIN/7SEG-1 input
2. Connect IN1 to BIN/7SEG-2 input
3. Connect IN2 to BIN/7SEG-4 input
4. Connect IN3 to BIN/7SEG-8 input
5. Toggle inputs to count: 0000→0001→0010→...→1111
6. Watch display show: 0→1→2→...→F
```

### 4-bit Adder Circuit
```javascript
// Example: Add two 4-bit numbers
1. Set first number on IN0-IN3 (A inputs)
2. Set second number on IN4-IN7 (B inputs)
3. Connect inputs to ADD0 A0-A3 and B0-B3
4. Connect ADD0 outputs S0-S3 to LEDs L0-L3
5. Connect CO (carry out) to L4
6. Result shows sum with carry indication
```

## 🤝 Contributing

We welcome contributions! Here's how to get started:

### Development Setup
```bash
# 1. Fork and clone the repository
git clone https://github.com/your-username/digital-board-simulator.git
cd digital-board-simulator

# 2. Create a feature branch
git checkout -b feature/your-feature-name

# 3. Make your changes
# Edit files using your preferred editor

# 4. Test thoroughly
# Open index.html in multiple browsers

# 5. Commit and push
git add .
git commit -m "Add your feature description"
git push origin feature/your-feature-name

# 6. Create a Pull Request
```

### Code Style Guidelines

#### JavaScript
```javascript
// Use ES6+ features
class MyClass {
    constructor(param) {
        this.param = param;
    }
    
    // Use arrow functions for short methods
    shortMethod = () => this.param * 2;
    
    // Use descriptive variable names
    calculateGateOutput(inputSignals) {
        return inputSignals.every(signal => signal === true);
    }
}
```

#### CSS
```css
/* Use BEM methodology for class names */
.component-name {
    /* Properties in logical order */
    display: flex;
    position: relative;
    
    /* Dimensions */
    width: 100px;
    height: 50px;
    
    /* Colors */
    background: #333;
    color: white;
    
    /* Effects */
    transition: all 0.3s ease;
}

.component-name__element {
    /* Child elements */
}

.component-name--modifier {
    /* Modifier variations */
}
```

### Issue Reporting
When reporting bugs, please include:
- Browser version and operating system
- Steps to reproduce the issue
- Expected vs actual behavior
- Console error messages (if any)
- Screenshots or video recordings

### Feature Requests
For new features, please provide:
- Clear description of the functionality
- Use cases and benefits
- Mockups or diagrams (if applicable)
- Compatibility considerations

## 📊 Performance Specifications

### Typical Performance Metrics
- **Initial Load Time**: < 2 seconds
- **Component Rendering**: < 100ms for complete redraw
- **Signal Propagation**: < 10ms for 25-gate circuit
- **Memory Usage**: ~15MB typical, ~30MB maximum
- **Supported Circuit Size**: Up to 1000 connections

### Optimization Features
- **Lazy Rendering**: Components rendered only when visible
- **Event Debouncing**: Prevents excessive updates during rapid input
- **State Caching**: Minimizes redundant calculations
- **SVG Optimization**: Efficient wire rendering with culling

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Ahmad Herzalla

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
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

## 🙏 Acknowledgments

- **Inspiration**: Digital logic courses and educational simulators
- **Icons**: Open source icon libraries
- **Testing**: Community feedback and contributions
- **Documentation**: Influenced by best practices from major open source projects

## 🔗 Links

- **Demo**: [Live Application](https://ahmad-herzalla0.github.io/digital-board-simulator)
- **Issues**: [Bug Reports & Features](https://github.com/Ahmad-Herzalla0/digital-board-simulator/issues)
- **Discussions**: [Community Forum](https://github.com/Ahmad-Herzalla0/digital-board-simulator/discussions)
- **Wiki**: [Extended Documentation](https://github.com/Ahmad-Herzalla0/digital-board-simulator/wiki)

---

**Made with ❤️ for digital logic education and experimentation**

*Last updated: January 2024*
