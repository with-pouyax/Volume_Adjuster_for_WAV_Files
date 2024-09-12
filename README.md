<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Volume Adjuster for WAV Files</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            color: #333;
        }
        h1 {
            color: #4CAF50;
        }
        code {
            background-color: #f4f4f4;
            border: 1px solid #ddd;
            padding: 2px 4px;
            border-radius: 4px;
        }
        pre {
            background-color: #f4f4f4;
            padding: 10px;
            border-radius: 4px;
            border: 1px solid #ddd;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
        ul {
            margin-left: 20px;
        }
        .example {
            background-color: #e8f5e9;
            padding: 10px;
            border-left: 4px solid #4CAF50;
            margin-top: 10px;
        }
        .command {
            background-color: #f9f9f9;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-bottom: 10px;
        }
        footer {
            margin-top: 40px;
            font-size: 0.9em;
            color: #555;
        }
    </style>
</head>
<body>

<h1>Volume Adjuster for WAV Files</h1>

<p>This C program adjusts the volume of a given WAV file by a specified factor.</p>

<h2>Overview</h2>

<p>The program reads a WAV file's audio data, scales it by a user-provided factor, and writes the modified audio data to a new output WAV file. It preserves the original WAV file’s header information, ensuring that the output file remains a valid WAV file.</p>

<h2>Usage</h2>

<p>To run the program, use the following syntax:</p>

<pre><code>./volume input.wav output.wav factor</code></pre>

<ul>
    <li><strong>input.wav</strong>: The path to the input WAV file.</li>
    <li><strong>output.wav</strong>: The path to the output WAV file where the modified audio will be saved.</li>
    <li><strong>factor</strong>: The volume adjustment factor (e.g., <code>0.5</code> to reduce the volume by half, <code>2.0</code> to double the volume).</li>
</ul>

<div class="example">
    <h3>Example:</h3>
    <pre><code>./volume original.wav adjusted.wav 1.5</code></pre>
    <p>This command will increase the volume of <code>original.wav</code> by 1.5 times and save the result to <code>adjusted.wav</code>.</p>
</div>

<h2>Compilation</h2>

<p>You can compile the program using <code>gcc</code>:</p>

<pre><code>gcc -o volume volume.c</code></pre>

<h2>Error Handling</h2>

<p>The program handles errors such as:</p>
<ul>
    <li>Incorrect number of arguments: It expects exactly 3 arguments (input file, output file, and factor).</li>
    <li>If the input or output files cannot be opened, it will display an error message.</li>
</ul>

<h2>How It Works</h2>

<ol>
    <li>The program reads the 44-byte header of the WAV file (standard for WAV files).</li>
    <li>It copies the header directly to the output file.</li>
    <li>It reads the audio samples (stored as 16-bit signed integers) from the input file, scales them by the factor, and writes the scaled samples to the output file.</li>
</ol>

<h2>Limitations</h2>

<p>Note that this program only works with:</p>
<ul>
    <li>16-bit WAV files with a standard 44-byte header.</li>
    <li>Extreme values for the volume factor may cause audio clipping or distortion.</li>
</ul>

<h2>License</h2>

<p>This project is licensed under the MIT License.</p>

<footer>
    <p>Created by pouya &bull; <a href="https://github.com/with-pouyax">GitHub</a></p>
</footer>

</body>
</html>
