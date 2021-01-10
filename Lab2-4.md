# 啟用複寫

- 選取 [Lab1](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Lab1.md) 中建立的復原保存庫。<br>

- 在刀鋒視窗(Blade)中找到「已複寫的項目」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image24.jpg)<br>

- 在「來源」中，選取「內部部署」，然後選取「來源位置」中的 Configuration Server。<br>
  
  - 在「機器類型」，選取「虛擬機器」。<br>
  
  - 在「vCenter/vSphere Hypervisor」中，選取 vSphere 主機，或可管理該主機的 vCenter 伺服器。<br>

  - 選取 處理序伺服器 (依預設安裝在組態伺服器 VM 上)。然後選取「確定」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image25.jpg)<br>
  
- 在「目標」中，選取您想要在其中建立容錯移轉 VM 的訂用帳戶和資源群組。 

  - 選取為 Resource Manager 部署模型。<br>

  - 選取 Azure VM 容錯移轉後所要連線的 Azure 網路和子網路。<br>

    「立即設定選取的機器] 會將網路設定套用到您啟用複寫的所有 VM 上。 
  
    「稍後設定」則可選取每部機器的 Azure 網路。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image26.jpg)<br>

- 在「虛擬機器」> 「選取虛擬機器」中，選取您要複寫的每部機器。 您只能選取可以啟用複寫的機器，然後選取「確定」。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image27.jpg)<br>

- 在「屬性」 > 「設定屬性」中，選取受控硬碟」快取儲存體帳戶與處理序伺服器要用來在電腦上自動安裝行動服務的帳戶。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image28.jpg)<br>

- 在「複寫設定」 > 「設定複寫設定」 中，確認[Lab2-3](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Lab2-3.md)中建立完成的複寫原則。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image29.jpg)<br>

- 最後，選取「啟用複寫」，當複寫啟用完成後，可以在套用複寫的VM中看到Agent已正確被安裝完成。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image30.jpg)<br>

- 當然，到「已複寫的項目」中，也可以看到方才的VM已經正常依據複寫原則同步中。<br>

  註：可能需要 15 分鐘或更久的時間，變更才會生效並顯示「已複寫的項目」中。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image31.jpg)<br>

- 您可以在「Site Recovery 作業」中，追蹤「啟用保護」作業的狀態與進度。<br>
 
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab15.jpg)<br>
  
完成後前往下一步 [Lab 3](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Lab3.md) 測試容錯移轉。
  
