import cv2
import numpy as np
from matplotlib import pyplot as plt

img=cv2.imread('notebook.png')
rows,cols,ch = img.shape

pts1 = np.float32([[245,160],[788,197],[108,941],[796,1005]])
pts2 = np.float32([[0,0],[500,0],[0,700],[700,700]])
M = cv2.getPerspectiveTransform(pts1,pts2)
dst = cv2.warpPerspective(img,M,(500,700))
plt.subplot(121),plt.imshow(img),plt.title('Input')
plt.subplot(122),plt.imshow(dst),plt.title('Output')
plt.show()

\<img width="1915" height="1017" alt="Image" src="https://github.com/user-attachments/assets/a3477122-24c5-4e3d-9560-57f84069d8ec" />





![Image](https://github.com/user-attachments/assets/2066ec15-34ea-4833-9dfb-e397317268b8)
