

## 프로젝트 소개
<img src="https://github.com/yoon3208/test-repository/assets/161405457/1d0a7566-a929-4b56-999b-93d8c85f8737" width="509">


- 프로젝트 소개
    - 프로젝트명 : N2FLIX
    - 프로젝트 내용 : 영화 예매하는 어플
    - 팀
        - 팀명 : N2
        - 팀원 : 조현민,김생근,이정복,박윤희,송정훈
            - 현민 → 로그인 페이지
            - 생근 → 세부페이지, 예매페이지
            - 정복 → 마이페이지
            - 윤희 → 검색페이지, 개봉 예정페이지
            - 정훈 → 메인페이지
              
## 와이어 프레임
<img width="618" alt="스크린샷 2024-04-28 오후 5 27 14" src="https://github.com/yoon3208/test-repository/assets/161405457/fcd7d942-f21f-4705-aed7-2f7448f45ef5">
<img width="288" alt="스크린샷 2024-04-29 오전 9 15 02" src="https://github.com/yoon3208/test-repository/assets/161405457/4b0c6872-aa38-40cd-982b-5ec3abd0cfdd">


# Coding Convention

- **코드 레이아웃**
    
    ### **1️⃣ 코드 레이아웃: 코드의 가독성을 높이기 위해 설정해 주는 규칙**
    
    ---
    
    | 들여쓰기 | ✔️ 들여쓰기는 탭(tab) 대신 2개의 space를 사용한다. |  |
    | --- | --- | --- |
    | 띄어쓰기 | ✔️ 콜론을 쓸 때는 콜론 오른쪽 부분만 띄어서 쓴다. | let names: [String: String] |
    | 줄바꿈 | ✔️ 함수 정의/호출 코드가 최대 길이를 초과하는 경우에 파라미터 이름을 기준으로 줄바꿈한다.✔️ 단, 파라미터에 클로저가 2개 이상 중첩될 경우에 무조건 줄을 바꿔서 사용한다.✔️ if-let, guard-let 구문이 길 경우 줄바꿈하고 한 칸 들여쓴다. | UIView.animate(  withDuration: 0.25,  animations: {    // 줄 바꿔서 코드 작성  }) |
    | 최대 줄 길이 | ✔️ 한 줄은 최대 99자를 넘지 않아야 한다. |  |
    | 빈 줄 | ✔️ 빈 줄에는 공백이 포함되서는 안된다.✔️ 모든 파일은 빈 줄로 끝나야 한다.✔️ MARK 구문 위, 아래에는 공백을 준다. | // MARK: - View Life Cycleoverride func viewDidLoad() { .. } |
    | 임포트 | ✔️ 모듈의 임포트는 알파벳 순으로 정렬한다.✔️ 단, 내장 프레임워크를 먼저 임포트하고, 외장 프레임워크는 빈 줄로 구분 후 임포트할 수 있도록 한다. | import UIKitimport SnapKitimport Then |
    
    ### **2️⃣ 네이밍: 직관성을 위해 정하는 규칙**
    
    ---
    
    Swift 네이밍의 공통으로 적용되는 규칙은, Python에서 사용하는 snake_case 대신 CamelCase를 사용해서 네이밍을 한다는 것이다.또한, 이름만 보았을 때에도 직관적으로 어떤 역할을 하는 인스턴스, 메서드인지 알아들을 수 있도록 하는 것이 핵심이다.
    
    - lowerCamelCase: 함수, 메소드, 변수, 상수 등에 사용
    - UpperCamelCase: 클래스, 구조체, 열거형, Extension 등에 사용
    
    | 클래스와 구조체 | ✔️ UpperCamelCase를 사용하며, 클래스 이름은 접두사를 붙이지 않는다. | class SomeClass { ... } |
    | --- | --- | --- |
    | 함수 | ✔️ LowerCamelCase를 사용한다.✔️ 함수 이름 앞에는 되도록 get을 붙이지 않도록 한다.✔️ Action 함수의 네이밍은 "주어 + 동사 + 목적어" 형태를 사용한다.    1) Tab은 .touchUpInside에 대응, Press는 .touchDown Events에 대응한다.    2) will~은 특정 행위가 일어나기 "직전"을 의미    3) did~는 특정 행위가 일어난 "직후"를 의미    4) should~는 대개 Bool을 반환하는 함수에 사용 | func backButtonDidTap() {  ...} |
    | 변수/상수 | ✔️ LowerCamelCase를 사용한다. | var someVar = 0let someVar = 0 |
    | 열거형 | ✔️ enum의 이름은 UpperCamelCase를 사용한다.✔️ enum의 각 case는 lowerCamelCase를 사용한다. | enum Result {  case .success  case .failure} |
    | 프로토콜 | ✔️ UpperCamelCase를 사용한다.✔️ 프로토콜을 채택할 때는 콜론과 빈칸을 넣어 구분한다. (띄어쓰기 규칙 동일) | extension VC: SomeProtocol { ... } |
    | 약어 | ✔️ 약어로 시작하는 경우에 소문자로 표기하고, 그 외에 경우에는 항상 대문자로 표기한다. | let userID: Intvar urlString: String |
    
    ### **3️⃣ 클로저**
    
    ---
    
    | ✔️ 파라미터와 리턴 타입이 없는 클로저는 () -> Void를 사용한다. | let someClosure: (() -> Void)? |
    | --- | --- |
    | ✔️ 클로저 정의 시 파라미터에는 괄호를 사용하지 않는다. | { make in ... } (O)   { (make) in ... } (X) |
    | ✔️ 클로저 정의 시 가능한 경우 타입 정의를 생략한다. | completion: { (make: Bool) -> Void in  ..}  // 이렇게 사용하지 말라는 뜻! |
    | ✔️ 클로저 호출 시 또다른 유일한 클로저를 마지막 파라미터로 받는 경우, 파라미터 이름을 생략한다. | 후행 클로저 적용하라는 뜻! |
    
    ### **4️⃣ 클래스와 구조체**
    
    ---
    
    | ✔️ 클래스와 구조체 내부에는 self를 명시적으로 사용한다. |  |
    | --- | --- |
    | ✔️ 구조체를 생성할 때는 Swift 구조체 생성자를 사용한다. | let frame = CGRect(x: ..., y: ...) |
    
    ### **5️⃣ 타입**
    
    ---
    
    | Array | ✔️ Array 타입은 Array<T>보다 [T]를 사용하도록 한다. | let names: [String] |
    | --- | --- | --- |
    | Dictionary | ✔️ Dictionary 타입은 Dictionary<T: U>보다 [T: U]를 사용하도록 한다. | let names: [Int: String] |
    
    ### **6️⃣ 주석: 내 코드를 다른 협업하는 개발자들에게도 잘 설명할 수 있는 방법!**
    
    ---
    
    | ✔️ 주석 표시 이후에는 한 칸 띄어쓰기 후, 내용을 작성한다. |  |
    | --- | --- |
    | ✔️ // MARK: - 를 사용하여 연관된 코드와 연관되지 않은 코드를 구분하도록 한다. | // MARK: - View Life Cycle |
    | ✔️ /// 를 사용해서 퀵헬프 주석을 남긴다. |  |
    
    ### **7️⃣ 프로그래밍시 추가 권장사항: 권장사항이긴 하지만 어지간하면 지키는 것이 좋다!**
    
    ---
    
    | 변수 초기화 | ✔️ 변수를 정의할 때 함께 초기화하도록 한다. | let label = UILabel.then {  $0.textColor = ... } |
    | --- | --- | --- |
    | enum 활용 | ✔️ 상수를 정의할 때, struct 대신 enum을 사용해서 모아둔다.✔️ 재사용성과 유지보수 측면, 그리고 생성자가 제공되지 않는 자료형을 사용하기 위해서이다. | private enum Color {  static let mainColor = ...} |
    | final 키워드 | ✔️ 더 이상 상속이 발생하지 않는 클래스는 항상 final 키워드로 선언한다. | final class ViewController { ... } |
    | 프로토콜 extension | ✔️ 프로토콜을 적용했을 때 관련 메서드는 extension으로 모아둔다. | extension VC: UITableViewDelegate { ... } |
    | 생명주기 | ✔️ 생명 주기에는 최대한 코드를 간결하게 작성한다. |  |

# Git

ex) [feat] alert action 추가

- `feat` : 새로운 기능 추가
- `fix` : 버그 수정
- `docs` : 문서 수정
- `style` : 코드 포맷팅, 세미콜론 누락, 코드 변경이 없는 경우
- `refactor` : 코드 리펙토링
- `test` : 테스트 코드, 리펙토링 테스트 코드 추가
- `chore` : 빌드 업무 수정, 패키지 매니저 수정
- `add` : 파일, 기타요소 추가

# 개발기능
  
- 로그인 화면/회원가입 화면(조현민)
    - [x]  회원가입 버튼을 누르면 아이디와 비밀번호를 입력받아 회원가입을 하고, 완료되면 다시 로그인 화면으로 이동합니다(아이디와 비밀번호 이외에 다른 정보들을 받아도 됩니다)
        - [x]  아이디(이메일 형식 확인, x버튼 클릭시 다 지우기)
        - [x]  비밀번호(눈 버튼 클릭시 비밀번호 표시)
    - [x]  로그인이 완료되면 UserDefault에 아이디와 비밀번호를 저장해서 이후 로그인할 때 아이디와 비밀번호가 자동으로 입력되어 있도록 합니다.
    - [x]  로그인이 완료되면 영화목록페이지로 전환
    - [x]  필수 기능 요소
        - `UserDefaults`를 활용하여 아이디와 비밀번호, 기타 정보를 저장해주세요.
- 영화 목록 페이지(송정훈)
    - [x]  하단 **TapBar의 첫번째 화면**입니다.
    - [x]  영화 이미지들은 좌우 스크롤 가능하도록 구현해주세요
    - [x]  API
    - https://developer.themoviedb.org/reference/movie-upcoming-list
    - [x]  `UITableView`를 활용하여 영화 포스터 카테고리별로 분류
    - [x]  `UICollectionView`를 활용하여 영화 포스터 가로 스크롤
    - [x]  사용자가 직접 상호 작용할 수 있는 다양한 기능을 제공해보세요.
- 개봉예정 페이지?(박윤희)
    - [x]  하단 **TapBar의 두번째 화면**입니다.
    - [x]  `UICollectionView` 를 활용하여 현재 날짜에서 (Date) 가장 가까운 순으로 제공
    - [x]  UIVisualEffectView를 활용하여 뒤에 있는 이미지 blur처리
    - [x]  포스터 클릭 시 해당 세부페이지로 이동(present)
- 찜목록 페이지(이정복)
    - [x]  하단 **TapBar의 세번째 화면**입니다.
    - [x]  `UICollectionView`를 활용하여 찜한 영화 표시
    - [x]  `UISwipeGestureRecognizer` 를 이용하여 위로 스와이프시 셀 제거
- 영화 세부 페이지(김생근)
    - [x]  영화를 클릭시 영화의 세부 페이지로 이동해주세요
        - [x]  로딩화면 구현
    - [x]  영화의 정보를 함께 페이지에 보여주세요
    - [x]  예매하기 버튼
    - [x]  찜하기 버튼
- 영화 예매 입력 페이지(김생근)
    - [x]  영화 세부 페이지에서 예매하기 버튼 클릭시 해당 페이지로 이동해주세요
    - [x]  `UIPickerView` 를 활용하여 시간 선택하도록 구현 !????????????
        - [x]  `UIDatPickerView`를 이용해 구현했습니다.
            - [x]  현재 시간을 기준으로 2주뒤 까지 선택이 가능하게 구현했습니다.
    - [x]  결제하기 버튼을 누르면 결제 내역이 마이페이지에서 보이도록 해주세요
- 영화 검색 페이지(박윤희)
    - [x]  상단 **돋보기버튼 클릭시 화면**입니다.
    - [x]  검색창에 텍스트를 입력하고 검색 버튼 클릭시 해당 텍스트가 포함된 영화들을 보여주세요
    - [x]  `UICollectionView`를 활용하여 영화 포스터를 표시
    - [x]  포스터 클릭시 해당 세부페이지로 이동 (present)
- 마이 페이지(이정복)
    - [x]  마이페이지 버튼 클릭시 해당 페이지로 이동
    - [x]  나의 필요한 계정 정보들을 표시해주세요(회원가입시 받은 정보들 활용)
    - [x]  프로필 이미지
    - [x]  찜 리스트 보여주기
    - [x]  예매한 영화 내역을 볼 수 있도록 해주세요
    - [x]  로그아웃시 로그인 화면으로 전환
    - [x]  닉네임 설정
