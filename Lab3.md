# 測試容錯移轉

您可以執行測試容錯移轉，以驗證您的複寫和災害復原策略不會有資料遺失或停機時間。<br>

測試容錯移轉不會影響正在進行的複寫或生產環境。您可以在特定虛擬機器 (VM) 上執行測試容錯移轉，<br>

或在包含多部 VM 的復原計劃上執行測試容錯移轉。如果想要執行單一 VM 的測試容錯移轉，請依照這裡所述的步驟進行 - <br>

- 在 Azure 入口網站的 Site Recovery 中，按一下「已複寫的項目」> 「找到複寫的VM」> 點選「測試容錯移轉」。

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image32.jpg)<br>

- 選取要對其進行容錯移轉的「復原點」。 您可以使用下列其中一個選項：
  
  - 最新：此選項會先處理已傳送到 Site Recovery 服務的所有資料，先為每部 VM 建立復原點後再進行容錯移轉。<br>
   
    此選項會提供最低的 RPO (復原點目標)，因為在容錯移轉後建立的 VM 具有在觸發容錯移轉時複寫到 Site Recovery 的所有資料。<br>

  - 最近處理：此選項會將計劃中所有 VM 容錯移轉到 Site Recovery 所處理的最新復原點。<br>
  
    若要查看特定 VM 的最新復原點，請檢查 VM 設定中的「最新復原點」。<br>
  
    此選項提供低 RTO (復原時間目標)，因為無須花費時間處理未處理的資料。<br>
 
  - 最新應用程式一致：此選項會將計劃中所有 VM 容錯移轉到 Site Recovery 所處理的最新應用程式一致復原點。<br>
  
    若要查看特定 VM 的最新復原點，請檢查 VM 設定中的「最新復原點」。<br>
  
  - 自訂：使用這個選項來將特定 VM 容錯移轉至特定復原點。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image33.jpg)<br>
  
- 選取要在其中建立測試 VM 的 Azure 虛擬網路。<br>

  - Site Recovery 會嘗試在名稱相同的子網路中建立測試 VM，並使用 VM 的「計算與網路」設定中提供的 IP 位址。<br>
  
  - 如果用於測試容錯移轉的 Azure 虛擬網路中無法使用名稱相同的子網路，則會在依字母順序的第一個子網路中建立測試 VM。<br>
  
  - 如果在子網路中無法使用相同的 IP 位址，則 VM 會接收子網路中另一個可用的 IP 位址。 <br>
  
- 點選「完成」後，即開始進行容錯移轉測試。<br>

- 在「Site Recovery作業」> 「工作」中，您可以追蹤容錯移轉進度。<br>

  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image34.jpg)<br>

- 同時，您應該可以在 Azure Portal中，找到使用來測試的複本機器。<br>

- 若要在 Azure VM 上初始化 RDP/SSH 連線，您必須在容錯移轉之 VM 的網路介面上新增公用 IP 位址。

- 新增完畢後就可以按下「連接」，用 RDP/SSH 連線到 Windows/Linux VM 中。

- 當一切都如預期般運作時，請按一下「清除測試容錯移轉」。 這樣會刪除在測試容錯移轉期間所建立的 Azure VM 資源。
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image35.jpg)<br>
