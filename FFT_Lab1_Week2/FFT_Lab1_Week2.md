```python
import numpy as np
import matplotlib.pyplot as plt
from scipy import signal

t = np.linspace(0, 1, 500)
```

# One Sine Wave FFT


```python
s =   1*np.sin(1 * 2 * np.pi * t)
plt.ylabel("Amplitude")
plt.xlabel("Time [s]")
plt.plot(t, s)
plt.show()
```


    
![png](output_2_0.png)
    



```python
fft = np.fft.fft(s)
T = t[1] - t[0]  # sampling interval 
N = s.size

# 1/T = frequency
f = np.linspace(0, 1 / T, N)

plt.ylabel("Amplitude")
plt.xlabel("Frequency [Hz]")
plt.bar(f[:N // 2], np.abs(fft)[:N // 2] * 1 / N, width=1.5)  # 1 / N is a normalization factor
plt.show()
```


    
![png](output_3_0.png)
    


# Two Sine Waves FFT


```python
s =   1*np.sin(10 * 2 * np.pi * t) \
    + 1*np.sin(40 * 2 * np.pi * t)

plt.ylabel("Amplitude")
plt.xlabel("Time [s]")
plt.plot(t, s)
plt.show()
```


    
![png](output_5_0.png)
    



```python
fft = np.fft.fft(s)
T = t[1] - t[0]  # sampling interval 
N = s.size

# 1/T = frequency
f = np.linspace(0, 1 / T, N)

plt.ylabel("Amplitude")
plt.xlabel("Frequency [Hz]")
plt.bar(f[:N // 2], np.abs(fft)[:N // 2] * 1 / N, width=1.5)  # 1 / N is a normalization factor
plt.show()
```


    
![png](output_6_0.png)
    


# Multiple Sine Waves FFT


```python
s =   1*np.sin(1 * 2 * np.pi * t) \
    + 1*np.sin(40 * 2 * np.pi * t) \
    + 1 * np.sin(90 * 2 * np.pi * t)\
    + 1 * np.cos(150 * 2 * np.pi * t)

plt.ylabel("Amplitude")
plt.xlabel("Time [s]")
plt.plot(t, s)
plt.show()

```


    
![png](output_8_0.png)
    



```python

fft = np.fft.fft(s)
T = t[1] - t[0]  # sampling interval 
N = s.size

# 1/T = frequency
f = np.linspace(0, 1 / T, N)

plt.ylabel("Amplitude")
plt.xlabel("Frequency [Hz]")
plt.bar(f[:N // 2], np.abs(fft)[:N // 2] * 1 / N, width=1.5)  # 1 / N is a normalization factor
plt.show()
```


    
![png](output_9_0.png)
    


# Low Frequency Square Waves FFT


```python
s=5*signal.square(1 * np.pi * 5 * t)

plt.ylabel("Amplitude")
plt.xlabel("Time [s]")
plt.plot(t, s)
plt.show()
```


    
![png](output_11_0.png)
    



```python
fft = np.fft.fft(s)
T = t[1] - t[0]  # sampling interval 
N = s.size

# 1/T = frequency
f = np.linspace(0, 1 / T, N)

plt.ylabel("Amplitude")
plt.xlabel("Frequency [Hz]")
plt.bar(f[:N // 2], np.abs(fft)[:N // 2] * 1 / N, width=1.5)  # 1 / N is a normalization factor
plt.show()
```


    
![png](output_12_0.png)
    


# High Frequency Square Waves FFT


```python
s=5*signal.square(10 * np.pi * 5 * t)

plt.ylabel("Amplitude")
plt.xlabel("Time [s]")
plt.plot(t, s)
plt.show()
```


    
![png](output_14_0.png)
    



```python
fft = np.fft.fft(s)
T = t[1] - t[0]  # sampling interval 
N = s.size

# 1/T = frequency
f = np.linspace(0, 1 / T, N)

plt.ylabel("Amplitude")
plt.xlabel("Frequency [Hz]")
plt.bar(f[:N // 2], np.abs(fft)[:N // 2] * 1 / N, width=1.5)  # 1 / N is a normalization factor
plt.show()
```


    
![png](output_15_0.png)
    


# What about a DC Signal


```python
s=np.repeat(5,t.shape[0])

plt.ylabel("Amplitude")
plt.xlabel("Time [s]")
plt.plot(t, s)
plt.show()
```


    
![png](output_17_0.png)
    



```python
fft = np.fft.fft(s)
T = t[1] - t[0]  # sampling interval 
N = s.size

# 1/T = frequency
f = np.linspace(0, 1 / T, N)

plt.ylabel("Amplitude")
plt.xlabel("Frequency [Hz]")
plt.bar(f[:N // 2], np.abs(fft)[:N // 2] * 1 / N, width=1.5)  # 1 / N is a normalization factor
plt.show()
```


    
![png](output_18_0.png)
    


# What about the inverse?


```python
from scipy import signal

s=signal.unit_impulse(800)

plt.plot(s)
```




    [<matplotlib.lines.Line2D at 0x7f94a06ddd30>]




    
![png](output_20_1.png)
    



```python
fft = np.fft.fft(s)
T = t[1] - t[0]  # sampling interval 
N = s.size

# 1/T = frequency
f = np.linspace(0, 1 / T, N)

plt.ylabel("Amplitude")
plt.xlabel("Frequency [Hz]")
plt.bar(f[:N // 2], np.abs(fft)[:N // 2] * 1 / N, width=1.5)  # 1 / N is a normalization factor
plt.show()
```


    
![png](output_21_0.png)
    



```python

```
