# Azure Site Recovery架構環境說明

Azure Site Recovery 服務可藉由協調虛擬機器與實體伺服器的複寫，進行容錯移轉及復原 (BCDR) 策略。<br>

一般而言，地端主機(On-premise, On-pre) 可以透過複寫Azure Site Recovery服務至 Azure，<br>

當On-pre的主機因不可抗拒之因素而停止供應服務時，便可利用Azure Site Recover容錯移轉，

開啟複寫至Azure 的VM來繼續供應服務。

當地端主機復原正常後，同樣再透過Azure Site Recovery容錯移轉將Azure VM複寫回到On-pre的主機，<br>

為您的事業連續性計畫(Business Continuity Plan, BCP)中的災害復原(Disaster Recovery, DR)做出貢獻。<br>

## Azure Site Recovery可以複寫哪些項目?

- 將 Azure VM 從一個 Azure 區域複寫至另一個 Azure 區域。<br>
- 將內部部署 VMware VM、Hyper-V VM、實體伺服器 (Windows 和 Linux)、Azure Stack VM 複寫至 Azure。<br>
- 將 AWS Windows 執行個體複寫到 Azure。<br>
- 將 System Center VMM 管理的內部部署 VMware VM、Hyper-V VM 和實體伺服器複寫至次要站台。<br>

## Azure Site Recovery (Azure VM to Azure VM)的架構圖

![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/architect1.jpg)


## Azure Site Recovery (VMWare to Azure VM)的架構圖

![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/architect1.1.jpg)

建立復原服務保存庫，請[前往 Lab1-1](https://github.com/MarkChang-Core/ASR-VMWare/edit/main/Lab1.md)開始。<br>
