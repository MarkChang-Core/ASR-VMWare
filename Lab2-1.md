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

- 在Site Recovery保存庫中，選擇左側刀鋒視窗(Blade) > Site Recovery 基礎結構，<br>
  
  並選擇其中的「對於VMWare與實體機器」 > 「Configuration Servers」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab6.jpg)<br>

- 點選「+ 伺服器」後，確認「伺服器類型」中為「VMWare的設定伺服器」後，選擇「下載範本」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab7.jpg)<br>

  註：此處為翻譯問題，設定伺服器即為組態伺服器，原文為Configuration Servers。<br>

## 在VMWare中匯入組態伺服器OVF範本

- 透過VMWare vSphere Client端登入VMWare vCenter或vSphere ESXi。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image1.jpg)<br>

- 在需要部署的機器中，點擊滑鼠右鍵選取 Deploy OVF Templete 以啟動「佈署OVF範本精靈」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image2.jpg)<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image3.jpg)<br>

- 在「Local file」上，選擇方才下載的 OVF Templete 路徑與檔案後，點擊「Next」。<br>

- 在「Select a name and folder」中，輸入希望建立的VM名稱後，點擊「Next」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image4.jpg)<br>

- 在「Select a compute resource」中，直接點選「Next」。

- 在「Review details」中，確認部署資訊無誤後，點選「Next」。

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image5.jpg)<br>

- 在「Select storage」中，將 Virtual Disk formay 調整為「Thin Provision」後，點選「Next」。<br>

  註：你也可以選擇「Thick Provision Eager Zeroed」，以達到最佳效能。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image6.jpg)<br>

- 在「Select networks」中，直接點選「Next」。<br>

- 在「Ready to complete」中，直接點選「Next」。<br>

等待Deploy完成後，前往下一步 [Lab 2-2](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Lab2-2.md) 繼續註冊組態伺服器。
