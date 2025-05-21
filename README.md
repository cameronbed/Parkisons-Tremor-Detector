# Tremor Detection with FFT on Circuit Playground

**Tremor Detection with FFT** is an embedded system project that leverages the Adafruit Circuit Playground's accelerometer and onboard peripherals to detect potential tremors using Fast Fourier Transform (FFT). This project demonstrates signal processing on a microcontroller and integrates real-time sensor analysis, user interaction, and output feedback through LEDs and sound.

## Installation

1. Clone the repository.
2. Import the project into PlatformIO on VSCode
3. Select the correct board and port, then upload to the Circuit Playground board.

## Features

* **Real-Time Accelerometer Sampling**: Captures 3-axis motion data at 40Hz.
* **FFT-Based Analysis**: Applies a Fourier Transform to determine signal frequency components.
* **Tremor Frequency Detection**: Identifies tremors in the 3–6 Hz band, typical of hand tremors.
* **Visual & Audio Feedback**:
  * Neopixels light up in color patterns based on detection strength.
  * Speaker tones (optional) can indicate detection events.
* **User Controls**:
  * Right button starts monitoring.
  * Left button stops and resets analysis.
* **Serial Debugging**: Frequency data is streamed via Serial Monitor and is compatible with Teleplot for visualization.

## Technologies Used

* **Board**: Adafruit Circuit Playground Classic
* **Language**: C++
* **Libraries**:
  * [Adafruit\_CircuitPlayground](https://github.com/adafruit/Adafruit_CircuitPlayground)
  * [arduinoFFT](https://github.com/kosme/arduinoFFT)

* **Tools**:
  * PlatformIO on VSCode
  * Teleplot VSCode Integration (for live graphing via serial)

## How It Works

1. **Sampling**: Accelerometer data is continuously collected and stored.
2. **Windowing**: A Hamming window is applied to smooth data before FFT.
3. **FFT**: Converts time-domain data into frequency-domain to detect signal peaks.
4. **Peak Analysis**: If a dominant frequency within the tremor band (3–6 Hz) exceeds a threshold, the system triggers feedback.
5. **Feedback**: Visual indicators and optional speaker tones respond to detection.

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
