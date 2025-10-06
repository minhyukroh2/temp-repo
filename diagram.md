```mermaid
graph TD
    subgraph "자동화 영역 (Batch Pipeline)"
        A["Windows 작업 스케줄러 <br> (매일 지정된 시간)"] --> B["배치 프로그램 <br> (run_batch_final.py)"];
        B --> C{"데이터 소스 <br> (KRX 정보데이터시스템)"};
        B --> D["데이터베이스 <br> (MS-SQL Server)"];
    end

    subgraph "데이터베이스"
        D -- "저장 프로시저 호출" --> E["Stored Procedure <br> usp_InsertDailyStockPrice <br> (UPSERT 로직)"];
        E --> F["테이블 <br> DailyStockPrice"];
    end

    subgraph "서비스 영역 (API Pipeline)"
        G["최종 사용자 / 서비스 <br> (웹 브라우저, BI툴 등)"] -- "HTTP 요청" --> H["피딩 프로그램 <br> (run_api.py / Flask)"];
        H -- "실시간 SQL 조회" --> D;
    end

    % --- 다크 모드를 위한 스타일 정의 ---
    style A fill:#d4edda,stroke:#155724,color:#000
    style B fill:#f8f9fa,stroke:#343a40,color:#000
    style C fill:#e0f7fa,stroke:#006064,color:#000
    style D fill:#fff3cd,stroke:#856404,color:#000
    style E fill:#e9ecef,stroke:#343a40,color:#000
    style F fill:#e9ecef,stroke:#343a40,color:#000
    style G fill:#f8d7da,stroke:#721c24,color:#000
    style H fill:#cce5ff,stroke:#004085,color:#000
```
