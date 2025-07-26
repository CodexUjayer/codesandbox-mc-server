#!/bin/bash

# Display the banner
cat << "EOF"
 /$$   /$$ /$$$$$$ /$$   /$$  /$$$$$$         /$$$$$$   /$$$$$$  /$$   /$$ /$$       /$$$$$$ /$$$$$$$$ /$$$$$$ /$$$$$$$$ /$$$$$$$ 
| $$  /$$/|_  $$_/| $$$ | $$ /$$__  $$       /$$__  $$ /$$__  $$| $$  | $$| $$      |_  $$_/| $$_____/|_  $$_/| $$_____/| $$__  $$
| $$ /$$/   | $$  | $$$$| $$| $$  \__/      | $$  \__/| $$  \ $$| $$  | $$| $$        | $$  | $$        | $$  | $$      | $$  \ $$
| $$$$$/    | $$  | $$ $$ $$| $$ /$$$$      |  $$$$$$ | $$  | $$| $$  | $$| $$        | $$  | $$$$$     | $$  | $$$$$   | $$  | $$
| $$  $$    | $$  | $$  $$$$| $$|_  $$       \____  $$| $$  | $$| $$  | $$| $$        | $$  | $$__/     | $$  | $$__/   | $$  | $$
| $$\  $$   | $$  | $$\  $$$| $$  \ $$       /$$  \ $$| $$  | $$| $$  | $$| $$        | $$  | $$        | $$  | $$      | $$  | $$
| $$ \  $$ /$$$$$$| $$ \  $$|  $$$$$$/      |  $$$$$$/|  $$$$$$/|  $$$$$$/| $$$$$$$$ /$$$$$$| $$       /$$$$$$| $$$$$$$$| $$$$$$$/
|__/  \__/|______/|__/  \__/ \______/        \______/  \______/  \______/ |________/|______/|__/      |______/|________/|_______/ 
 
                                                   
EOF

echo "🚀 Updating system packages..."
apt update

echo "🔧 Installing required packages..."
apt install -y sudo
apt install -y systemctl

echo "🌐 Adding PufferPanel repository..."
curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh?any=true | sudo bash

echo "📦 Updating package list..."
sudo apt update

echo "🎮 Installing PufferPanel..."
sudo apt-get install -y pufferpanel

echo "👤 Creating a PufferPanel user..."
sudo pufferpanel user add

echo "✅ Enabling and starting PufferPanel service..."
sudo systemctl enable --now pufferpanel

echo "🔥 PufferPanel is installed and running!"
echo "Subscribe To @SanjitGamingYT"
