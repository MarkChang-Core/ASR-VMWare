# 啟用複寫

- 選取 [複寫應用程式] > [來源] 。<br>

- 在 [來源] 中，選取 [內部部署] ，然後選取 [來源位置] 中的組態伺服器。<br>

- 在 [機器類型] 中，選取 [虛擬機器]。<br>

- 在 [vCenter/vSphere Hypervisor] 中，選取 vSphere 主機，或可管理該主機的 vCenter 伺服器。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab12.jpg)<br>
  
- 選取處理序伺服器 (依預設安裝在組態伺服器 VM 上)。然後選取[確定]。選擇狀況良好的處理序伺服器。<br>

- 在 [目標] 中，選取您想要在其中建立容錯移轉 VM 的訂用帳戶和資源群組。 我們會使用 Resource Manager 部署模型。<br>

- 選取 Azure VM 容錯移轉後所要連線的 Azure 網路和子網路。<br>

- 選取 [立即設定選取的機器] ，將網路設定套用到您啟用複寫的所有 VM 上。 選取 [稍後設定] 以選取每部機器的 Azure 網路。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab13.jpg)<br>

- 在 [虛擬機器] > [選取虛擬機器] 中，選取您要複寫的每部機器。 您只能選取可以啟用複寫的機器，然後選取 [確定]。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab14.jpg)<br>

- 在 [屬性] > [設定屬性] 中，選取處理序伺服器要用來在電腦上自動安裝行動服務的帳戶。<br>

- 在 [複寫設定] > [設定複寫設定] 中，確認已選取正確的複寫原則。<br>

- 選取 [啟用複寫] 。 Site Recovery 會在 VM 已啟用複寫時安裝行動服務。<br>

- 您可以在 [復原服務保存庫] > [監視] > [Site Recovery 作業] 中，追蹤 [啟用保護] 作業的進度。<br>

- 執行 [完成保護] 作業之後，機器即準備好進行容錯移轉。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab15.jpg)<br>
  
- 可能需要 15 分鐘或更久的時間，變更才會生效並顯示[已複寫的項目]中。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab16.jpg)<br>
  
完成後前往下一步 [Lab 3](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Lab3.md) 測試容錯移轉。
  
