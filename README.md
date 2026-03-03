# image-enhance
import cv2
import numpy as np
import matplotlib.pyplot as plt


img = cv2.imread("straw.jpg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


img_float = img.astype(np.float32)


alpha = 1.5  # Contrast control (1.0-3.0)
beta = 30  # Brightness control (0-100)

enhanced = alpha * img_float + beta


enhanced = np.clip(enhanced, 0, 255)
enhanced = enhanced.astype(np.uint8)
plt.imshow(enhanced)
plt.title("Brightness and Contrast")
plt.axis("off")
plt.show()
