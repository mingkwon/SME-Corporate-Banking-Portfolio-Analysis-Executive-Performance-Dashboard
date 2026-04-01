# SME-Corporate-Banking-Portfolio-Analysis-Executive-Performance-Dashboard

Dataset: https://www.kaggle.com/datasets/examsgovt/sme-financial-decision-risk-prediction-dataset


// 1. Tỷ lệ Distress tổng thể
Distress Rate % = 
DIVIDE(
    SUM(sme_clean[Financial_Distress]),
    COUNTROWS(sme_clean)
) * 100

// 2. Số lượng SME
Total SMEs = COUNTROWS(sme_clean)

// 3. Average Liquidity
Avg Liquidity Score = AVERAGE(sme_clean[Liquidity_Score])

// 4. Average Risk Score
Avg Risk Score = AVERAGE(sme_clean[Risk_Score])

// 5. High Risk SMEs
High Risk SMEs = 
CALCULATE(
    COUNTROWS(sme_clean),
    sme_clean[Financial_Distress] = 1
)
