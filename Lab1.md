# Azure Site Recovery架構環境說明

Azure Site Recovery 服務可藉由協調虛擬機器與實體伺服器的複寫、容錯移轉及復原 (BCDR) 策略，平時地端主機可以使用複寫Azure Site Recovery服務至 Azure，<br>
地端的主機因不可抗拒之因素而停止服務時，便可使用Azure Site Recover容錯移轉將開啟複寫至Azure 的VM來繼續服務，等地端主機復原後，<br>
使用Azure Site Recovery容錯移轉將Azure的VM複寫到地端的主機，為您的商務持續性與災害復原做出貢獻。<br>

## Azure Site Recovery可以複寫哪些項目?

- 將 Azure VM 從一個 Azure 區域複寫至另一個 Azure 區域。<br>
- 將內部部署 VMware VM、Hyper-V VM、實體伺服器 (Windows 和 Linux)、Azure Stack VM 複寫至 Azure。<br>
- 將 AWS Windows 執行個體複寫到 Azure。<br>
- 將 System Center VMM 管理的內部部署 VMware VM、Hyper-V VM 和實體伺服器複寫至次要站台。<br>

## Azure Site Recovery 的架構圖

![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/architect1.jpg)

 > **Tips.如果** <br>
 
 完成後，請[前往 Lab1-2](https://g)。<br>
