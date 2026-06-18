# machicafe
graph TD
    %% Start Process
    Start([アプリ起動]) --> CheckLocation{現在地設定済み？}
    
    %% Location Check
    CheckLocation -- Yes --> Home[ホーム画面]
    CheckLocation -- No --> SetLocation[現在地設定]
    SetLocation --> Home
    
    %% Home Screen Routes
    Home --> End([アプリ終了])
    Home --> Search[検索機能]
    Home --> List[一覧機能]
    
    %% Search Flow
    Search --> CheckSearch{検索を実行?}
    CheckSearch -- No --> Home
    CheckSearch -- Yes --> Input[条件・キーワード入力]
    Input --> SearchResult[検索結果]
    SearchResult --> CheckDetailSearch{詳細を見る?}
    CheckDetailSearch -- No --> Search
    CheckDetailSearch -- Yes --> Detail[詳細画面]
    
    %% List Flow
    List --> ListView[一覧画面]
    ListView --> CheckDetailList{詳細を見る?}
    CheckDetailList -- No --> List
    CheckDetailList -- Yes --> Detail
