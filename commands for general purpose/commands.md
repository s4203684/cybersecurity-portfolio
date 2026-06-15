# Installing clamaAV Anti-Virus
sudo apt install clamav clamav-daemon

# Update virus definitions
sudo freshclam

# Runnig Mannual Anti-Virus Scan with Clamav
clamscan -r --bell -i /home/your_username