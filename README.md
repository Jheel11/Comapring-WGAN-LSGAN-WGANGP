

# Comparative Analysis of LSGAN, WGAN, and WGAN-GP on MedMNIST Dataset

This project presents a comparative study of three prominent GAN variants—**LSGAN**, **WGAN**, and **WGAN-GP**—on the **MedMNIST** dataset. We evaluate the models based on **Inception Score (IS)** and **Fréchet Inception Distance (FID)** to assess the quality and diversity of the generated medical images. Additionally, **TensorBoard** is integrated to monitor training metrics in real time.

---

## 📊 Objective

To implement, train, and compare the performance of:
- Least Squares GAN (LSGAN)
- Wasserstein GAN (WGAN)
- Wasserstein GAN with Gradient Penalty (WGAN-GP)

on the MedMNIST dataset with consistent architecture, hyperparameters, and training epochs.

---

##  Dataset

- **Dataset**: [MedMNIST](https://medmnist.com/)
- **Subset Used**: PneumoniaMNIST
- **Preprocessing**: Rescaled to 1-channel 28×28 images
- **Use Case**: Benchmarking GAN performance in medical image synthesis

---

## 🚀 GAN Architectures

All three models share the same generator and discriminator architecture:
- **Generator**: Deep CNN with transposed convolutions
- **Discriminator**: CNN with LeakyReLU activations

Each model differs in its **loss function** and **training method**:
- LSGAN uses Least Squares loss
- WGAN uses Wasserstein loss with weight clipping
- WGAN-GP uses Wasserstein loss with gradient penalty

---

## 📈 TensorBoard Integration

TensorBoard is used to visualize:
- Generator and discriminator loss curves
- Training stability and convergence
- Real-time sample generation tracking

To launch TensorBoard, run:

```bash
tensorboard --logdir=runs
```

---

## 🏁 Training Configuration

- **Epochs**: 50  
- **Batch Size**: 64  
- **Latent Dimension (z)**: 100  
- **Learning Rate**: 0.0002  
- **Optimizers**:
  - LSGAN: Adam (β1 = 0.5, β2 = 0.999)
  - WGAN: RMSProp
  - WGAN-GP: Adam (β1 = 0.5, β2 = 0.999)

---

## 📊 Results Summary

| **Model**   | **Inception Score (IS)** | **Fréchet Inception Distance (FID)** |
|-------------|---------------------------|---------------------------------------|
| **WGAN-GP** | 2.9967                    | 26.5000                               |
| **WGAN**    | 2.1909                    | 26.5000                               |
| **LSGAN**   | 1.8297                    | 26.5000                               |

> ✅ **Conclusion**: WGAN-GP shows the best generative quality, outperforming both LSGAN and WGAN in terms of IS and FID.

---

## 📂 Directory Structure

```
├── models/                 # Saved model checkpoints
├── outputs/                # Generated image samples per epoch
├── runs/                   # TensorBoard logs
├── data/                   # Processed MedMNIST dataset
├── lsgan_train.py
├── wgan_train.py
├── wgan_gp_train.py
├── utils.py
├── evaluate.py
└── README.md
```

---

## ✅ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/medmnist-gan-comparison.git
   cd medmnist-gan-comparison
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Train a model:
   ```bash
   python lsgan_train.py
   python wgan_train.py
   python wgan_gp_train.py
   ```

4. Launch TensorBoard:
   ```bash
   tensorboard --logdir=runs
   ```

---
## 📜 License

This project is licensed under the MIT License.

```
