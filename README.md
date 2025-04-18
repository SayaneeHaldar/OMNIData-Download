# OMNIData-Download

import spacepy.omni as omni
import datetime as dt
import matplotlib.pyplot as plt

# Define time range
start = dt.datetime(202*, **, **)
end = dt.datetime(202*, **, **)

# Download data
data = omni.get_omni(start, end, dbase='omni_min')

# Plot key parameters
fig, axs = plt.subplots(4, 1, figsize=(12, 10), sharex=True)

axs[0].plot(data['Epoch'], data['Vx'], label='Solar Wind Speed (km/s)', color='blue')
axs[0].legend(); axs[0].grid()

axs[1].plot(data['Epoch'], data['BZ_GSM'], label='IMF Bz (nT)', color='green')
axs[1].legend(); axs[1].grid()

axs[2].plot(data['Epoch'], data['Dst'], label='Dst Index (nT)', color='red')
axs[2].legend(); axs[2].grid()

axs[3].plot(data['Epoch'], data['AE'], label='AE Index (nT)', color='purple')
axs[3].legend(); axs[3].grid()

plt.suptitle('OMNI Solar Wind & Geomagnetic Data (** **–**, 202*)')
plt.xlabel('Date')
plt.tight_layout()
plt.show()
