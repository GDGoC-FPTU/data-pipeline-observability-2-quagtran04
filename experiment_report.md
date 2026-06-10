# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600798
**Name:** Tran Van Quang
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc validate nen Agent chon san pham electronics hop ly nhat theo logic gia cao nhat. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Du lieu rac co outlier cuc lon nen Agent chon mot san pham phi thuc te, kem theo duplicate id, wrong type va null values. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai hoac bi loi khi dung Garbage Data vi chat luong du lieu dau vao khong con dang tin cay. Trong file rac, cot `price` co gia tri chu nhu `ten dollars`, lam pandas doc cot nay thanh kieu du lieu khong phu hop de so sanh va tim gia tri lon nhat. Duplicate ID lam mot ma san pham dai dien cho nhieu mat hang khac nhau, khien truy vet va giai thich ket qua bi nhieu. Null values lam thieu thong tin quan trong nhu category hoac id, trong khi outlier nhu `Nuclear Reactor` gia 999999 co the lam Agent uu tien mot record phi thuc te. Khi pipeline khong validate va transform du lieu truoc, Agent co the dua ra cau tra loi sai, khong lien quan, hoac bi crash ngay trong buoc tinh toan.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt tot giup Agent hieu yeu cau, nhung neu du lieu bi sai kieu, bi thieu, trung lap hoac co outlier qua lon thi Agent van co the tra loi sai. Data quality la nen tang de pipeline va Agent tao ra ket qua dang tin cay.
