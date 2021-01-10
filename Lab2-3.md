# 建立複寫原則

- 開啟 Azure 入口網站，然後選取 [所有資源]。<br>

- 選取先前建立的復原服務保存庫。<br>

- 若要建立複寫原則，請選取 [Site Recovery 基礎結構] > [複寫原則] > [+ 複寫原則] 。<br>

  - 在 [建立複寫原則] 中，輸入原則名稱(例如：VMwareRepPolicy)。<br>

  - 在 [RPO 閾值] 中，使用預設值 60 分鐘。 這個值可定義復原點的建立頻率。 連續複寫超過此限制時會產生警示。<br>

  - 在 [復原點保留] 中，指定每個復原點的保留時間長度。例如使用 72 小時。 複寫的 VM 可以還原至保留期內的任何時間點。<br>

  - 在 [應用程式一致快照集頻率] 中，指定建立應用程式一致快照集的頻率。 我們會使用預設值 60 分鐘。 選取 [確定] 以建立原則。<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Image/image22.jpg)<br>
  
- 此原則會自動與設定伺服器產生關聯。<br>

- 依預設會自動建立容錯回復的比對原則。例如，如果複寫原則是 rep-policy，容錯回復原則就會是 rep-policy-failback。<br>
  
  註：從 Azure 起始容錯回復時才會使用此原則。<br>
  
完成後前往下一步 [Lab 2-4](https://github.com/MarkChang-Core/ASR-VMWare/blob/main/Lab2-4.md) 啟用複寫。
