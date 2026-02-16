# PDF Learning using GAN (NO₂ Data)

## Objective
Learn the probability density function (PDF) of a transformed variable using only data samples and a Generative Adversarial Network (GAN), without assuming any parametric distribution.

---

## Dataset
- Source: India Air Quality Dataset (Kaggle)
- Feature used: **NO₂ concentration (x)**

---

## Transformation

The variable x is transformed into z using:

z = x + a_r sin(b_r x)

Parameters are computed using roll number **r = 102317253**

- a_r = 0.5 × (r mod 7) = **0.5**
- b_r = 0.3 × (r mod 5 + 1) = **1.2**

Final transformation:

z = x + 0.5·sin(1.2x)

---

## GAN Approach

**Generator**
- Input: Random noise N(0,1)
- Output: Synthetic z samples

**Discriminator**
- Classifies samples as real (data) or fake (generated)

Both networks are trained adversarially so the generator learns the distribution of z from data only.

---

## PDF Estimation

After training:
- Large number of samples generated from GAN
- PDF estimated using histogram density
- Plot saved as: `pdf_z_histogram.png`

---

## Observations

- Major density peak successfully captured
- Training stabilized after initial oscillations
- Generated distribution closely matches transformed data shape

---

## Key Point

GAN can learn an unknown PDF directly from samples without assuming Gaussian or other parametric models.

