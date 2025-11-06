# Burpsuite_Pro_setting_Up_Linux 


- Linux arm pro
  - https://portswigger.net/burp/releases#professional	
  - <img width="1499" height="894" alt="圖片" src="https://github.com/user-attachments/assets/108fc97b-058d-4384-a7dc-f6d393b6f5d1" />

	```bash
		cd /home/parallels/Downloads
	```

	```shell
		chmod +x burpsuite_pro_linux_arm64_v2025_9_5.sh
	```


	```shell
		sudo ./burpsuite_pro_linux_arm64_v2025_9_5.sh
	```

	```shell
		/usr/bin/BurpSuitePro
	```

	- <img width="555" height="482" alt="圖片" src="https://github.com/user-attachments/assets/af979f30-2ce1-4f6b-b4ea-f9daf6cb8e63" />

	- <img width="556" height="474" alt="圖片" src="https://github.com/user-attachments/assets/b0f33510-5f72-48d1-b0e3-2450cb62ce52" />

	
		```shell
			cd /usr/bin/BurpSuitePro
		```
		- put the BurpPro.jar into the linux 
		- <img width="591" height="394" alt="圖片" src="https://github.com/user-attachments/assets/a2291152-5dcc-4531-af86-d4c13f606e7b" />

	   ```shell
			sudo git clone https://github.com/NeoIsBackAgain/Burpsuite_Pro_setting_Up.git;cd Burpsuite_Pro_setting_Up
		```
		```shell
			sudo mv BurpLoaderKeygen.jar /usr/bin/BurpSuitePro
		```
	
	
		```shell
			sudo apt install openjdk-17-jdk
		```
	
	
	
		```shell
			java -jar BurpLoaderKeygen.jar
		```
	
	
		- <img width="1486" height="691" alt="圖片" src="https://github.com/user-attachments/assets/909023a1-a262-4705-9b5a-15191def284b" />

		- <img width="1478" height="655" alt="圖片" src="https://github.com/user-attachments/assets/3321ed59-b4e3-4960-bff0-3346b2b6f080" />

		- <img width="626" height="543" alt="圖片" src="https://github.com/user-attachments/assets/2ae277d4-40ba-4dcb-a9e6-f7f144c305a1" />

		- <img width="584" height="471" alt="圖片" src="https://github.com/user-attachments/assets/595a302b-c021-4074-b9b5-d9a61629bf67" />

		- <img width="1492" height="616" alt="圖片" src="https://github.com/user-attachments/assets/c3e43147-fa0f-4302-972b-ee9848f5f9d8" />

	
		```shell
			vim /usr/bin/BurpSuitePro/run-burp.sh
  			#!/usr/bin/env bash
			# wrapper to run Burp with your interactive environment and keep terminal
			# change if you use zsh/other shell
			
			# load profile (optional)
			if [ -f "$HOME/.profile" ]; then
			  source "$HOME/.profile"
			fi
			# load bashrc for interactive env variables (optional)
			if [ -f "$HOME/.bashrc" ]; then
			  source "$HOME/.bashrc"
			fi
			
			# optional: cd to Burp folder so relative paths behave same as terminal
			cd /usr/bin/BurpSuitePro || true
			
			# run java (replace args if needed)
			exec /usr/bin/BurpSuitePro/jre/bin/java \
			  --add-opens=java.desktop/javax.swing=ALL-UNNAMED \
			  --add-opens=java.base/java.lang=ALL-UNNAMED \
			  --add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED \
			  --add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED \
			  --add-opens=java.base/jdk.internal.org.objectweb.asm.Opcodes=ALL-UNNAMED \
			  -javaagent:/usr/bin/BurpSuitePro/BurpLoaderKeygen.jar \
			  -noverify -jar /usr/bin/BurpSuitePro/burpsuite_pro.jar

		```
	
	
		```shell
			mkdir -p ~/.local/share/applications
			cat > ~/.local/share/applications/burpsuite-pro.desktop <<'EOF'
			[Desktop Entry]
			Type=Application
			Name=Burp Suite Professional
			Comment=Run Burp Suite Professional (via wrapper)
			Exec=/usr/bin/BurpSuitePro/run-burp.sh
			Terminal=true
			Icon=/usr/bin/BurpSuitePro/.install4j/BurpSuitePro.png
			Categories=Development;Security;
			StartupWMClass=install4j-burp-StartBurp
			MimeType=application/x-extension-burp;
			EOF
			
			chmod 644 ~/.local/share/applications/burpsuite-pro.desktop
		```
	
	
	<img width="1571" height="850" alt="圖片" src="https://github.com/user-attachments/assets/326c2f6e-3b06-4b7e-8f34-2ab6c87e9fb0" />

	- <img width="1552" height="673" alt="圖片" src="https://github.com/user-attachments/assets/b5e09081-fee5-40cb-83a4-f0c39eafb51e" />

