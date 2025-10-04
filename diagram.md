```mermaid
graph TD
    A[전체 고객 데이터] --> B[Part 1: RFM 클러스터링];
    B --> C[고객 페르소나 정의];
    
    D[특정 상품 데이터] --> E[Part 2: 재구매 주기 분석];
    E --> F[재구매 임박 고객 정의];
    
    subgraph MERGE & ACTION
        C --> G{최종 타겟 고객 추출};
        F --> G;
        G --> H[개인화 마케팅 실행];
    end

    %% --- 스타일 정의 (다크 모드용) ---
    %% 글자색은 박스 배경색에 맞춰 어둡게 유지
    %% 테두리(stroke)와 화살표(link)는 어두운 배경에 잘 보이도록 밝은 회색으로 변경
    
    style A fill:#81D4FA,stroke:#BDBDBD,color:#212121,stroke-width:2px
    style D fill:#81D4FA,stroke:#BDBDBD,color:#212121,stroke-width:2px
    style H fill:#A5D6A7,stroke:#BDBDBD,color:#212121,stroke-width:2px
    style G fill:#FFF59D,stroke:#BDBDBD,color:#212121,stroke-width:2px
    
    linkStyle default stroke:#BDBDBD,stroke-width:2px
'''
