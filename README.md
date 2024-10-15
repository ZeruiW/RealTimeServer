
# Real-Time Video Processing with TimesFormer

This project implements a real-time video processing system using TimesFormer for video classification and attention visualization. It consists of a client-server architecture that allows for streaming video frames and processing them in real-time.

## Technology Stack

- **Python**: The primary programming language used.
- **PyTorch**: Deep learning framework for running the TimesFormer model.
- **OpenCV (cv2)**: Used for image processing and video handling.
- **ZeroMQ (zmq)**: Provides the messaging layer for client-server communication.
- **PyAV (av)**: Used for video encoding and decoding.
- **Transformers**: Hugging Face's library for accessing pre-trained models.
- **NumPy**: For numerical operations on arrays.
- **Matplotlib & Seaborn**: For creating visualizations.
- **SciPy**: Used for signal processing (smoothing and peak detection).


`requirements.txt` file includes the core libraries needed to run your real-time video processing system. Users can install these dependencies using pip:

```
pip install -r requirements.txt
```

Note that some of these packages (especially PyTorch) might have specific version requirements or installation procedures depending on the user's system and CUDA version. You might want to add a note in your README about this, suggesting users visit the official PyTorch website to get the appropriate installation command for their system.


## Key Components

1. **VideoClient**: Streams video frames to the server.
2. **VideoServer**: Receives frames, processes them using TimesFormer, and generates visualizations.
3. **AttentionExtractor**: Wrapper for the TimesFormer model to extract attention maps.

## Features

- Real-time video streaming and processing
- Attention heatmap visualization
- Temporal attention visualization
- Frame-by-frame attention analysis
- Video classification using TimesFormer

## Usage

### Starting the Server

Run the following command to start the server:

```bash
python realtimeserver.py
```

The server will start and listen on port 6000 for incoming video streams.

### Running the Client

To stream a video file to the server, use the following command:

```bash
python realtimeclient.py --video /path/to/your/video.mp4
```

For example:

```bash
python realtimeclient.py --video ./-0ew-c0w7uc.mp4
```

You can also specify a different server address if needed:

```bash
python realtimeclient.py --video ./-0ew-c0w7uc.mp4 --server 192.168.1.100
```

### Output

The server will process the incoming video stream and generate the following outputs in the `Realtime` directory:

- `output.mp4`: Processed video with attention heatmaps
- `temporal_visualization.png`: Graph showing temporal attention over time
- `frames_visualization.png`: Sampled frames with attention heatmaps
- `attention_data.json`: JSON file containing frame-by-frame attention data
- `frames/`: Directory containing individual frame images with attention heatmaps

## Notes

- Ensure that you have the necessary dependencies installed before running the scripts.
- The TimesFormer model (`facebook/timesformer-base-finetuned-k400`) will be downloaded automatically on first run.
- Processing speed may vary depending on your hardware capabilities, especially GPU availability.

```
