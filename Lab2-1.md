# Azure Site Recovery 保存庫 (VMWare)

在您的來源環境中，您需要單一、高可用性、內部部署的電腦來下列裝載 Site Recovery 元件，這些元件包含有：<br>

- 組態伺服器(Configuration Servers)︰組態伺服器會協調內部部署與 Azure 之間的通訊，以及管理資料複寫。<br>

- 處理序伺服器：處理序伺服器可作為複寫閘道。 負責接收複寫資料，以快取、壓縮和加密進行最佳化，<br>

  然後將其傳送至 Azure 中的快取儲存體帳戶。<br>
  
  處理序伺服器也會在您要複寫的 VM 上安裝行動服務代理程式，並且在內部部署 VMware VM 上執行自動探索。<br>
  
- 主要目標伺服器：主要目標伺服器會在從 Azure 容錯回復期間，處理複寫資料。<br>

  這些元件會全部一起安裝在單一內部部署機器 (也稱為「組態伺服器」 ) 上。 根據預設，對於 VMware 災害復原，<br>

  我們會將組態伺服器設定為高可用性 VMware VM。 若要這麼做，請下載備妥的開放式虛擬化應用程式 (OVA) 範本，<br>
  
  然後將範本匯入 VMware 以建立 VM。<br>

## 下載 VM 範本

Step 1. 在Site Recovery保存庫中，選擇左側刀鋒視窗(Blade) > Site Recovery 基礎結構，<br>

並選擇其中的「對於VMWare與實體機器」 > 「Configuration Servers」。<br>

![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab6.jpg)

Step 2. 點選「+ 伺服器」後，確認「伺服器類型」中為「VMWare的設定伺服器」後，選擇「下載範本」。

![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab7.jpg)

  註：此處為翻譯問題，設定伺服器即為組態伺服器，原文為Configuration Servers

## 在VMWare中匯入組態伺服器OVF範本

Step 1. 透過VMWare vSphere Client端登入VMWare vCenter或vSphere ESXi。<br>

Step 2. 在檔案(File)中，選取佈署OVF範本(Deploy OVF Templete)以啟動「佈署OVF範本精靈」。<br>

![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab8.jpg)

Step 3. 在「選取來源」上，選擇方才下載的OVF範本位置。

Step 4. 在「檢閱詳細資料」上，直接選取「下一步」。

Step 5. 在「選取名稱和資料夾」、「選取組態」中，直接接受預設設定。

Step 6. 在「選取儲存體」上，於「選取虛擬磁碟格式」中，請選擇為「Thick Provision Eager Zeroed」，以達到最佳效能。

Step 7. 在範本精靈中的其他設置步驟頁面中，均已預設值選定後並執行「下一步」。

Step 8. 在「準備完成」頁面中，若使用為預設值設定VM，請選取「在佈署後開啟電源」，並點選「完成」。


完成後前往下一步 [Lab 2-2](https://github.com/MarkChang-Core/ASR-VMWare/edit/main/Lab2-2.md) 繼續註冊組態伺服器。
