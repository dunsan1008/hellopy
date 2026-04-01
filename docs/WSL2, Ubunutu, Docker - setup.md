이 문서는 Windows 환경에서 개발자가 WSL2 기반 Ubuntu와 Docker를 설치하여  
Codespaces와 유사한 개발 환경을 구성할 수 있도록 안내합니다.

# 1) WSL2 활성화

PowerShell(관리자 권한)에서 실행: wsl --install
또는 수동 설치: dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart


WSL 기본 버전을 2로 설정: wsl --set-default-version 2
  
# 2) Ubuntu 설치

1. Microsoft Store 실행  
2. “Ubuntu 22.04 LTS” 검색  
3. 설치 후 실행  
4. 사용자 이름/비밀번호 설정

# 3) 패키지 업데이트

sudo apt update sudo apt upgrade -y 실행

# 4) Docker 설치
 4-1) Docker 저장소 추가: sudo apt install ca-certificates curl gnupg -y

sudo install -m 0755 -d /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# 5) Docker 데몬 실행
 - sudo service docker start

부팅 시 자동 실행: sudo systemctl enable docker

# 6) sudo 없이 docker 명령 사용
 - sudo usermod -aG docker $USER

적용을 위해 WSL 재시작: wsl --shutdown

# 7) Docker 동작 확인
 - docker run hello-world
