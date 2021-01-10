# 設定 Configuration Server

### 安裝 Configuration Server

- VM 會開機進入 Windows Server 2016 安裝體驗。 接受授權合約，並建立系統管理員密碼。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image7.jpg)<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image8.jpg)<br>
  
- 在安裝完成之後，以系統管理員身分登入 VM。<br>

- 您第一次登入時，Azure Site Recovery 設定工具會在數秒內啟動。<br>

- 輸入用來向 Site Recovery 註冊設定伺服器的名稱。 然後，選取 [下一步]。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image9.jpg)<br>

- 建立連線之後，選取[登入]以登入您的 Azure 訂用帳戶，認證必須能夠存取您要在其中註冊組態伺服器的保存庫。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image10.jpg)<br>
  
  接下來會進入配置機器名稱、配置身分至Azure AD以及設定Configuration Server的自動設定過程，完成後將自動重啟。<br>

### 設定 Configuration Server

- 重啟完成後，透過系統管理員身分登入，登入後預設將會自動透過 IE 開啟 Configuration Server設定精靈。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image11.jpg)<br>

- 確認「NIC」的資訊，選取 Configuration Server 與 Azure 連線使用的 NIC，確認無誤後，點選「Save」。<br>
   
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image12.jpg)<br>
  
- 在「Select Recovery Services vault」中，點選「Click to Sign in」，登入 Azure 帳號後，允許 Premission，<br>

  並選擇正確的訂閱與RG資訊，此處請特別留意 **一旦設定完成後即無法變更**，設定完成後點選「Continue」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image13.jpg)<br>
 
- 在「Install third-party software」中，接受授權合約，並選取「Download and install」以安裝 MySQL，<br>

  安裝完成後點選「Continue」。<br>

  註：如果您在路徑中放置 MySQL，則可略過此步驟。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image14.jpg)<br>

- 在「Validate appliance configuration」中，將會自動驗證您的配置，這將會需要一些時間等待，完成後點選「Continue」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image14.jpg)<br>

- 在「Configure vCenter Server/vSphere ESXi server credentials」中，點選「Add vCenter Server/vSphere ESXi server」，接著 - 。<br>

  - 輸入 vCenter Server 或 vSphere Server (準備複寫之 VM) 的 Server name 或 IP Address。<br>

  - 輸入伺服器所接聽的連接埠。<br>
  
  - 輸入要用於保存庫中 VMware 伺服器的好記名稱。<br>

  - 輸入可供設定伺服器用來連線至 VMware 伺服器的使用者認證。<br>
    
    (請確定使用者名稱和密碼都正確無誤，且屬於所要保護虛擬機器的 Administrators 群組。) <br>

  Azure Site Recovery 會使用這些資訊進行自動探索可用於複寫的 VMware VM。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image15.jpg)<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image16.jpg)<br>
  
  確認探索到的 VMware VM 無誤後，選取「Continue」。<br>

- 在「Configure virtual machine credentials」中，點選「Add virtual machine credentials」，請留意 -<br>
  
  - 若為 Windows 電腦，此帳戶需具備您要複寫之機器的本機系統管理員權限。<br>

  - 若為 Linux，請提供根帳戶的詳細資料。<br>
  
  輸入完成後，點選「Add」，回到主頁面後，點選「Continue」。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image17.jpg)<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image18.jpg)<br>

- 點選「Finalize configuration」以完成所有配置，。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image19.jpg)<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image20.jpg)<br>
  
- 註冊完成後，在 Azure 入口網站中確認組態伺服器和 VMware 伺服器都已列在保存庫中的 [來源] 頁面上。<br>
  
  然後選取 [確定] 以設定目標設定。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image21.jpg)<br>

  **註：可能需要 15 分鐘以上，帳戶名稱才會出現在入口網站。**

完成後前往下一步 [Lab 2-3](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Lab2-3.md) 建立複寫原則。
