# Computer-Vision-Labs
 import cv2
import numpy as np
import matplotlib.pyplot as plt


#Convert to grayscale
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

#Apply Gaussian blur
blur = cv2.GaussianBlur(gray, (5, 5), 0)

#Edge detection (Canny)
edges = cv2.Canny(blur, 100, 200)

#Combine images horizontally
combined = np.hstack((img, cv2.cvtColor(gray, cv2.COLOR_GRAY2BGR),
                      cv2.cvtColor(edges, cv2.COLOR_GRAY2BGR)))

#Convert BGR to RGB for matplotlib display
combined_rgb = cv2.cvtColor(combined, cv2.COLOR_BGR2RGB)

#Show output using matplotlib
plt.figure(figsize=(12, 6))
plt.imshow(combined_rgb)
plt.axis('off')
plt.title("Original | Grayscale | Edges")
plt.show()

