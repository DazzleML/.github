# AI Training Monitor

**Monitor and visualize AI model training in real-time**

**[GitHub Repository](https://github.com/DazzleML/ai-training-monitor)** | **Status: Active**

> Track loss, learning rate, sample outputs, and system resources during AI model training.

---

## Features

### Real-time Monitoring
- Watch training progress live in your browser
- Auto-refresh dashboards
- Mobile-friendly interface
- No page refresh needed

### Loss Visualization
- Plot training and validation loss
- Multiple metrics on same graph
- Zoom and pan for detail
- Export plots as images

### Sample Tracking
- View generated samples during training
- Compare samples across epochs
- Track quality improvements
- Side-by-side comparisons

### Resource Monitoring
- GPU utilization percentage
- VRAM usage tracking
- GPU temperature monitoring
- CPU and system RAM usage

### Experiment Comparison
- Compare multiple training runs
- Overlay loss curves
- Hyperparameter comparison
- Performance metrics

### Export Reports
- Generate training summaries
- PDF/HTML reports
- Share with team
- Document experiments

---

## Use Cases

### Monitor Long Training Runs Remotely
```bash
# Start training with monitoring
python train.py --monitor localhost:8080

# Access from anywhere
ssh -L 8080:localhost:8080 server
# View at http://localhost:8080
```

### Catch Overfitting Early
- Watch validation vs training loss
- Get alerts when validation loss increases
- Save checkpoints automatically
- Stop training before waste

### Compare Hyperparameter Experiments
```bash
# Run multiple experiments
python train.py --lr 0.001 --name exp1 &
python train.py --lr 0.0001 --name exp2 &
python train.py --lr 0.00001 --name exp3 &

# Compare in dashboard
http://localhost:8080/compare?runs=exp1,exp2,exp3
```

### Debug Training Issues
- Identify loss spikes
- Track learning rate schedule
- Monitor gradient norms
- Detect NaN/Inf values

### Generate Training Reports
```bash
# After training completes
ai-training-monitor report --run experiment-123 \
  --output training_report.pdf
```

---

## Installation

```bash
# PyPI (coming soon)
pip install ai-training-monitor

# From source
git clone https://github.com/DazzleML/ai-training-monitor
cd ai-training-monitor
pip install -e ".[dev]"
```

---

## Usage

### Basic Usage

```bash
# Start training with monitoring
python train.py --monitor localhost:8080

# View in browser
http://localhost:8080/training/current
```

### Integration with PyTorch

```python
from ai_training_monitor import TrainingMonitor

# Initialize monitor
monitor = TrainingMonitor(port=8080)

# Training loop
for epoch in range(num_epochs):
    for batch in dataloader:
        loss = train_step(batch)

        # Log to monitor
        monitor.log_metric("loss", loss.item())
        monitor.log_metric("lr", optimizer.param_groups[0]['lr'])

    # Log epoch samples
    samples = generate_samples(model)
    monitor.log_images("samples", samples)
```

### Integration with TensorFlow

```python
from ai_training_monitor import TensorFlowCallback

# Add callback
callbacks = [
    TensorFlowCallback(port=8080)
]

model.fit(
    train_dataset,
    epochs=100,
    callbacks=callbacks
)
```

---

## Dashboard Features

### Main Dashboard
- Current loss plot
- Recent samples
- System resources
- Training progress

### Metrics View
- All logged metrics
- Customizable plots
- Zoom and pan
- Export as image

### Samples Gallery
- Generated samples grid
- Epoch comparison
- Full-screen view
- Download samples

### Experiments List
- All training runs
- Quick comparison
- Filter and search
- Archive old runs

---

## Technical Requirements

- Python 3.10+
- Web browser for visualization
- Training framework (PyTorch, TensorFlow, etc.)
- Optional: GPU for faster training

---

## License

GPL 3.0 - See repository for details

---

**Part of [DazzleML](https://github.com/DazzleML) - AI Development Tools**
