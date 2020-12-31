# Lab 1. Azure 基本環境設置

## 建立 Azure Recovery Services 保存庫

在建立 Azure Recovery Services的環境時，首先必須要先確保無論來自何處的VM均可有存放地點，

因此我們會先為其建立一個保存庫，而ASR的保存庫除了具備儲存的功能外，也具有協調與調整的控制介面。

1. 在[Azure Portal](https://portal.azure.com)中，搜尋「Recovery Services」，並選擇「Recovery Services 保存庫」。<br>

     ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab1.jpg)

2. 單擊「+ 新增」後，在必要資訊設置中，請選擇需要配置的「資源群組(Resource Group)」，或選擇「新建」以建立資源群組。<br>

3. 在「保存庫名稱」中，輸入可辨識的保存庫名稱。<br>

4. 在「區域」中，選擇您的保存庫需要建立的資料中心地理位置。<br>

     ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab2.jpg)

## 建立 Azure Network

無論來源伺服器是On-pre或是Cloud的VM，均會被複製到Azure受控磁碟，而當災難發生需要執行故障轉移時，<br>

便會透過這些受控磁碟建立Azure VM，而這個建立的過程將會選擇預先配置好的Azure Network。<br>

1. 在[Azure Portal](https://portal.azure.com)中，搜尋「Network」，並選擇「虛擬網路」<br>

     ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab3.jpg)

2. 單擊「+ 新增」後，在必要資訊設置中，請選擇需要配置的「資源群組(Resource Group)」，或選擇「新建」以建立資源群組。<br>

3. 在「名稱」中，輸入可辨識的VNET名稱，但需留意此VNET名稱於單一的Azure資源群組中，並須是獨一無二的。<br>
     
3. 在「區域」中，選擇您的虛擬網路需要建立的資料中心地理位置，但請留意，需與前面建立的ASR保存庫相同資料中心位置，<br>
   
   完成後請點選「下一步」配置IP位址與子網路(SubNet)。<br>
   
     ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab4.jpg)
     
4. 在IP位址中，輸入網路範圍，此Lab範例中建立為 10.0.0.0/16，SubNet則建立為 10.0.0.0/24，確認資訊後，請點選下一步設置安全性。<br>

     ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/lab5.jpg)

5. 在安全性中可選擇是否啟用Azure Bastion、DDoS Protection或Azure Firewall的設置，但由於此Lab聚焦於ASR，<>

   因此這邊直接點選「檢閱 + 建立」。<br>

開始設置Azure Site Recovery 保存庫，請[前往 Lab 2](https://github.com/MarkChang-Core/ASR-VMWare/edit/main/Lab1.md)開始。<br>
