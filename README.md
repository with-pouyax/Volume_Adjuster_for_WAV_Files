
# 🎵 WAV File Volume Adjuster

A simple C program to adjust the volume of a `.wav` audio file by a specified factor.

## 📋 Overview

This tool allows you to modify the volume of a WAV file. The program reads the audio data from the input WAV file, scales it by a user-defined factor, and outputs a new WAV file with the adjusted volume. The original WAV file's metadata (header) is preserved, ensuring the output remains a valid WAV file.

## 🚀 Getting Started

### Prerequisites

To use this program, you need to have the following:

- A C compiler like `gcc`
- A `.wav` file with a standard 44-byte header
- Basic knowledge of command-line usage

### Compilation

You can compile the source code with the following command:

```bash
gcc -o volume volume.c
```

This will create an executable called `volume` that you can use to run the program.

### Usage

Once compiled, the program is executed with three arguments:

```bash
./volume input.wav output.wav factor
```

- `input.wav`: Path to the input WAV file
- `output.wav`: Path to the output WAV file where the adjusted audio will be saved
- `factor`: A floating-point number specifying how much to scale the volume (e.g., `0.5` to reduce by half, `2.0` to double the volume)

#### Example:

```bash
./volume song.wav song_louder.wav 1.5
```

This command will increase the volume of `song.wav` by 1.5 times and save the result in `song_louder.wav`.

### Input Constraints

- The program expects a `.wav` file with a **44-byte header** (common for standard WAV files).
- The audio data should be in **16-bit signed integers**.

## ⚙️ How It Works

1. **Read the WAV header:** The first 44 bytes of the input file are the header, which contains metadata such as the file format and sample rate.
2. **Adjust the volume:** The audio data (stored as 16-bit samples) is read from the input file. Each sample is multiplied by the specified factor.
3. **Write the output file:** The adjusted samples are written to the output file, along with the original header.

## 🛠️ Error Handling

- If the correct number of arguments (3) is not provided, the program will display a usage message.
- If the input or output file cannot be opened, an error message will be shown.
  
## 🌟 Features

- **Volume scaling:** Amplify or reduce the audio by any floating-point factor.
- **Non-destructive:** The original WAV file remains unchanged.
- **Easy to use:** Straightforward command-line interface with error handling.

## ❗ Limitations

- Designed to work only with **16-bit PCM WAV files**.
- Modifying the volume by extreme factors (e.g., very high or very low) might cause audio clipping or distortion.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
