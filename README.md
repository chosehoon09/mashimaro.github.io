# mashimaro.github.io
```react
import React, { useState, useMemo } from 'react';
import { Search, BookOpen, Microscope, PenTool, GraduationCap, ChevronRight, Book, Library, Sparkles } from 'lucide-react';

const App = () => {
  const bookData = {
    humanities: [
      { id: 1, title: "논리와 비판적 사고", author: "김광수" },
      { id: 2, title: "한국 철학 에세이", author: "김교빈" },
      { id: 3, title: "설득의 논리학", author: "김용규" },
      { id: 4, title: "다문화 사회의 새로운 이해", author: "전숙자" },
      { id: 5, title: "논어", author: "김형찬(역)" },
      { id: 6, title: "뉴캐피털리즘", author: "리처드 세넷" },
      { id: 7, title: "소유냐 존재냐", author: "에리히 프롬" },
      { id: 8, title: "택리지", author: "이중환" },
      { id: 9, title: "일상에서 지리를 만나다", author: "이광렬" },
      { id: 10, title: "위대한 패배자", author: "볼프슈나이더" },
      { id: 11, title: "옛 그림 읽기의 즐거움", author: "오주석" },
      { id: 12, title: "미학오디세이 1 2 3", author: "진중권" },
      { id: 13, title: "한국의 교양을 읽는다 1~5", author: "김용석" },
      { id: 14, title: "공리주의", author: "밀" },
      { id: 15, title: "민주주의와 그 비판자들", author: "로버트 달" },
      { id: 16, title: "거꾸로 읽는 세계사", author: "유시민" },
      { id: 17, title: "교실밖 국사여행", author: "역사학연구소" },
      { id: 18, title: "그리스 로마 신화 1, 2", author: "이윤기" },
      { id: 19, title: "나의 문화유산답사기 1 2 3", author: "유홍준" },
      { id: 20, title: "내가 아는 것이 진리인가", author: "김창호" },
      { id: 21, title: "더불어 사는 인간과 자연", author: "박이문" },
      { id: 22, title: "동양 철학 에세이", author: "김교빈 외" },
      { id: 23, title: "로마인 이야기", author: "시오노나나미" },
      { id: 24, title: "바람의 딸 우리 땅에 서다", author: "한비야" },
      { id: 25, title: "박물관에서 꺼내온 철학 이야기", author: "이현구 외" },
      { id: 26, title: "백범 일지", author: "김구" },
      { id: 27, title: "사랑의 길 배움의 길", author: "남명 조식" },
      { id: 28, title: "삼국유사", author: "일연" },
      { id: 29, title: "성공하는 사람들의 7가지 습관", author: "스티븐코비" },
      { id: 30, title: "세계사 편력", author: "네루" },
      { id: 31, title: "소박한 풍경", author: "김기찬" },
      { id: 32, title: "국화와 칼", author: "루스 베네딕트" },
      { id: 33, title: "군주론", author: "마키아벨리" },
      { id: 34, title: "그들에게 국민은 없다", author: "노엄 촘스키" },
      { id: 35, title: "나는 빠리의 택시 운전사", author: "홍세화" },
      { id: 36, title: "달리는 기차 위에 중립은 없다", author: "하워드 진" },
      { id: 37, title: "매스 미디어와 사회", author: "최정호, 강현두" },
      { id: 38, title: "목민심서", author: "정약용" },
      { id: 39, title: "문명의 충돌", author: "새뮤얼 헌팅턴" },
      { id: 40, title: "홀로 벼슬하며 그대를 생각하노라", author: "정한권" },
      { id: 41, title: "21세기 키워드", author: "이인식" },
      { id: 42, title: "지학스님의 차", author: "지학" },
      { id: 43, title: "사랑의 기술", author: "에리히 프롬" },
      { id: 44, title: "서양 미술사", author: "에른스트 곰브리치" },
      { id: 45, title: "세상을 바꾸는 작은 관심", author: "에다드 레즈" },
      { id: 46, title: "국가", author: "플라톤" },
      { id: 47, title: "열린 사회와 그 적들", author: "칼 포퍼" },
      { id: 48, title: "공산당 선언", author: "칼 맑스" },
      { id: 49, title: "시장은 정말 우리를 행복하게 하는가", author: "이정전" },
      { id: 50, title: "문명 속의 불만", author: "지그문트 프로이드" },
      { id: 51, title: "나쁜 사마리아인들", author: "장하준" },
      { id: 52, title: "꿈의 해석", author: "지그문트 프로이드" },
      { id: 53, title: "노예의 길", author: "하이에크" },
      { id: 54, title: "건전한 사회", author: "에리히 프롬" },
      { id: 55, title: "성과 속", author: "미르치아 엘리아데" },
      { id: 56, title: "불안", author: "알랭 드 보통" },
      { id: 57, title: "검은 피부 하얀 가면", author: "프란츠 파농" },
      { id: 58, title: "문학과 예술의 사회사", author: "아르놀트 하우저" },
      { id: 59, title: "향연", author: "플라톤" },
      { id: 60, title: "서양미술사", author: "곰브리치" },
      { id: 61, title: "슬픈 열대", author: "C. 레비스트로스" },
      { id: 62, title: "실존주의는 휴머니즘 이다", author: "장 폴 사르트르" },
      { id: 63, title: "5백년 내력의 명문가 이야기", author: "조용헌" },
      { id: 64, title: "역사란 무엇인가", author: "E.H. 카어" },
      { id: 65, title: "윈스턴 처칠의 재치와 지혜", author: "제임스 C 흄스" },
      { id: 66, title: "정치와 삶의 세계", author: "김우창" },
      { id: 67, title: "죽음에 이르는 병", author: "키에르케고르" },
      { id: 68, title: "죽음의 수용소에서", author: "빅터 프랑클" },
      { id: 69, title: "치요택츠", author: "미국지리학회" },
      { id: 70, title: "철학 속의 논리", author: "황경식" },
      { id: 71, title: "철학 에세이", author: "조성오" },
      { id: 72, title: "철학의 모험", author: "이진경" },
      { id: 73, title: "청소년을 위한 철학 에세이", author: "강영계" },
      { id: 74, title: "한국사 신론", author: "이기백" },
      { id: 75, title: "소크라테스의 변명", author: "플라톤" },
      { id: 76, title: "소유의 종말", author: "제레미 리프킨" },
      { id: 77, title: "아름다운 삶, 사랑 그리고 마무리", author: "헬렌 니어링" },
      { id: 78, title: "에밀", author: "루소" },
      { id: 79, title: "여성학 강의", author: "한국여성연구회" },
      { id: 80, title: "영화의 이해", author: "루이스 자네티" },
      { id: 81, title: "유시민의 경제학 카페", author: "유시민" },
      { id: 82, title: "자연에 미친 사람", author: "톰 브라운" },
      { id: 83, title: "작은 것이 아름답다", author: "E.F 슈마허" },
      { id: 84, title: "제3의 물결", author: "앨빈 토플러" },
      { id: 85, title: "천년 궁궐을 짓는다", author: "신응수" },
      { id: 86, title: "침묵의 봄", author: "레이첼 카슨" },
      { id: 87, title: "텔레비전을 버려라", author: "제리 맨더" }
    ],
    science: [
      { id: 1, title: "과학 혁명의 구조", author: "토마스 S. 쿤" },
      { id: 2, title: "엔트로피", author: "제레미 리프킨" },
      { id: 3, title: "현대 물리학과 동양 사상", author: "프리초프 카프라" },
      { id: 4, title: "부분과 전체", author: "하이젠베르크" },
      { id: 5, title: "신비로운 숫자", author: "리오네 살렘" },
      { id: 6, title: "재미있는 화학여행", author: "김희준" },
      { id: 7, title: "유전자들의 전쟁", author: "이병훈" },
      { id: 8, title: "이기적 유전자", author: "리처드 도킨스" },
      { id: 9, title: "가야(살아있는 생명체로서의 지구)", author: "제임스 러브록" },
      { id: 10, title: "이야기 파라독스", author: "마틴 가드너" },
      { id: 11, title: "과학콘서트", author: "정재승" },
      { id: 12, title: "시간의 역사", author: "스티븐 호킹스" },
      { id: 13, title: "미래는 어떻게 존재하는가", author: "이인식" },
      { id: 14, title: "갈릴레오 갈릴레이", author: "브레히트" },
      { id: 15, title: "새로운 과학과 문명의 전환", author: "카프라" },
      { id: 16, title: "생명이란 무엇인가", author: "슈뢰딩거" },
      { id: 17, title: "수학 콘서트", author: "박경미" },
      { id: 18, title: "피보나치가 들려주는 피보나치 수열이야기", author: "오혜정" },
      { id: 19, title: "청소년이 꼭 알아야 할 수학 상식 68", author: "정구선" },
      { id: 20, title: "교과서를 만든 수학자들", author: "김화영" },
      { id: 21, title: "수학으로 생각한다", author: "고지마히로유키" },
      { id: 22, title: "달콤한 수학사(1-5)", author: "마이클 J. 브래들리" },
      { id: 23, title: "객관성의 칼날", author: "찰스 길리스피" },
      { id: 24, title: "인간은 기후를 지배할 수 있을까", author: "스티븐스" },
      { id: 25, title: "스카너의 심리상자 열기", author: "로렌 슬레이터" },
      { id: 26, title: "인간 본성에 대하여", author: "에드워드 윌슨" },
      { id: 27, title: "본성과 양육", author: "맷 리들리" },
      { id: 28, title: "괴델 에셔 바흐 나야 나 1 2", author: "호프스테터" },
      { id: 29, title: "브레인 스토리", author: "수잔 그린필드" },
      { id: 30, title: "코스모스", author: "칼 세이건" },
      { id: 31, title: "카오스", author: "제임스 글릭" },
      { id: 32, title: "같기도 하고 아니 같기도 하고", author: "로알드 호프만" },
      { id: 33, title: "확률의 도깨비", author: "붓총주" },
      { id: 34, title: "20세기 과학의 쟁점", author: "임경순" },
      { id: 35, title: "21세기와 자연 과학", author: "서울대 자연대 교수" },
      { id: 36, title: "털없는 원숭이", author: "데스먼드 모리스" },
      { id: 37, title: "현대 사회와 과학문명", author: "서울대학교 출판부" },
      { id: 38, title: "생명이 있는 것은 다 아름답다", author: "최재천" },
      { id: 39, title: "수학비타민", author: "박경미" },
      { id: 40, title: "즐거운 수학 사전", author: "테오니 파파스" },
      { id: 41, title: "카이스트 천재들의 수학 공식 7가지", author: "권승희" },
      { id: 42, title: "수학 판타지", author: "루돌프 카핑" },
      { id: 43, title: "페르마의 마지막 정리", author: "사이먼 싱" },
      { id: 44, title: "세상에서 가장 아름다운 수학 공식", author: "리오네 살렘" }
    ],
    literature: [
      { id: 1, title: "태백산맥", author: "조정래" },
      { id: 2, title: "혼불", author: "최명희" },
      { id: 3, title: "문학의 숲을 거닐다", author: "장영희" },
      { id: 4, title: "바리데기", author: "황석영" },
      { id: 5, title: "장미의 이름", author: "움베르토 에코" },
      { id: 6, title: "변신", author: "프란츠 카프카" },
      { id: 7, title: "한 줌의 모래", author: "컨싱국" },
      { id: 8, title: "방드르디", author: "미셸 투르니에" },
      { id: 9, title: "그리고 아무 말도 하지 않았다", author: "하인리히 뵐" },
      { id: 10, title: "그물에 걸리지 않는 바람처럼", author: "법정" },
      { id: 11, title: "나도 너에게 자유를 주고 싶다", author: "홍신자" },
      { id: 12, title: "난장이가 쏘아올린 작은 공", author: "조세희" },
      { id: 13, title: "느림", author: "밀란 쿤데라" },
      { id: 14, title: "데미안", author: "헤르만 헤세" },
      { id: 15, title: "동물 농장", author: "조지 오웰" },
      { id: 16, title: "먼 나라 이웃나라", author: "이원복" },
      { id: 17, title: "생의 한가운데", author: "루이제 린저" },
      { id: 18, title: "섬", author: "장 그르니에" },
      { id: 19, title: "삼국지", author: "나관중" },
      { id: 20, title: "상도", author: "최인호" },
      { id: 21, title: "소설 동의보감", author: "이은성" },
      { id: 22, title: "아명호 편지", author: "황대권" },
      { id: 23, title: "인연(외 수필)", author: "피천득" },
      { id: 24, title: "잡초는 없다", author: "윤구병" },
      { id: 25, title: "아큐정전", author: "노신" },
      { id: 26, title: "가난한 사람들", author: "도스토예프스키" },
      { id: 27, title: "강의-나의 동양고전 독법", author: "신영복" },
      { id: 28, title: "정지용 전집", author: "정지용" },
      { id: 29, title: "춘향전", author: "미상" },
      { id: 30, title: "모모", author: "미하엘 엔데" },
      { id: 31, title: "무기여 잘 있거라", author: "헤밍웨이" },
      { id: 32, title: "백범일지", author: "김구" },
      { id: 33, title: "뿌리", author: "알렉스 헤일리" },
      { id: 34, title: "어린 왕자", author: "생텍쥐페리" },
      { id: 35, title: "오래된 미래", author: "헬레나 노르베리 호지" },
      { id: 36, title: "외딴방", author: "신경숙" },
      { id: 37, title: "이방인", author: "까뮈" },
      { id: 38, title: "자전거 도둑", author: "박완서" },
      { id: 39, title: "전쟁과 평화", author: "레프 톨스토이" },
      { id: 40, title: "조지 오웰", author: "조지 오웰" },
      { id: 41, title: "주홍글씨", author: "호손" },
      { id: 42, title: "즐거운 편지", author: "황동규" },
      { id: 43, title: "천변풍경", author: "박태원" },
      { id: 44, title: "토지", author: "박경리" },
      { id: 45, title: "파우스트", author: "괴테" },
      { id: 46, title: "페스트", author: "까뮈" },
      { id: 47, title: "폭풍의 언덕", author: "에밀리 브론테" },
      { id: 48, title: "학의 마을", author: "이문열" },
      { id: 49, title: "해에게서 소년에게", author: "최남선" },
      { id: 50, title: "호밀밭의 파수꾼", author: "샐린저" }
    ],
    university: [
      { id: 1, title: "고함", author: "디기앤" },
      { id: 2, title: "과학혁명의 구조", author: "토마스 쿤" },
      { id: 3, title: "광장", author: "최인훈" },
      { id: 4, title: "구운몽", author: "김만중" },
      { id: 5, title: "국부론", author: "애덤 스미스" },
      { id: 6, title: "군주론", author: "마키아벨리" },
      { id: 7, title: "그리스 비극", author: "아이스킬로스 외" },
      { id: 8, title: "금강삼매경론", author: "원효" },
      { id: 9, title: "논어", author: "공자" },
      { id: 10, title: "돈키호테", author: "세르반테스" },
      { id: 11, title: "두보", author: "두보" },
      { id: 12, title: "루쉰 소설집", author: "루쉰" },
      { id: 13, title: "마의 산", author: "토마스 만" },
      { id: 14, title: "맹자", author: "맹자" },
      { id: 15, title: "목민심서", author: "정약용" },
      { id: 16, title: "무정", author: "이광수" },
      { id: 17, title: "미디어의 이해", author: "맥루한" },
      { id: 18, title: "백년의 고독", author: "마르케스" },
      { id: 19, title: "변신", author: "카프카" },
      { id: 20, title: "변신 이야기", author: "오비디우스" },
      { id: 21, title: "보바리 부인", author: "플로베르" },
      { id: 22, title: "사기", author: "사마천" },
      { id: 23, title: "삼국유사", author: "일연" },
      { id: 24, title: "삼대", author: "염상섭" },
      { id: 25, title: "설국", author: "가와바타 야스나리" },
      { id: 26, title: "성찰", author: "데카르트" },
      { id: 27, title: "성학십도", author: "이황" },
      { id: 28, title: "성학집요", author: "이이" },
      { id: 29, title: "셰익스피어 4대 비극", author: "셰익스피어" },
      { id: 30, title: "순수이성비판", author: "칸트" },
      { id: 31, title: "슬픈 열대", author: "레비스트로스" },
      { id: 32, title: "신곡", author: "단테" },
      { id: 33, title: "양철북", author: "귄터 그라스" },
      { id: 34, title: "엔트로피", author: "제레미 리프킨" },
      { id: 35, title: "역사", author: "헤로도토스" },
      { id: 36, title: "열하일기", author: "박지원" },
      { id: 37, title: "위대한 유산", author: "디킨스" },
      { id: 38, title: "안나 카레니나", author: "톨스토이" },
      { id: 39, title: "이기적 유전자", author: "도킨스" },
      { id: 40, title: "이백 시집", author: "이백" },
      { id: 41, title: "일리아드 오디세이", author: "호메로스" },
      { id: 42, title: "자본론", author: "마르크스" },
      { id: 43, title: "자유론", author: "밀" },
      { id: 44, title: "장자", author: "장자" },
      { id: 45, title: "적과 흑", author: "스탕달" },
      { id: 46, title: "젊은 예술가의 초상", author: "제임스 조이스" },
      { id: 47, title: "주역", author: "미상" },
      { id: 48, title: "주홍글씨", author: "호손" },
      { id: 49, title: "짜라투스트라는 이렇게 말했다", author: "니체" },
      { id: 50, title: "천변풍경", author: "박태원" },
      { id: 51, title: "체호프 희곡선", author: "안톤 체호프" },
      { id: 52, title: "카라마조프 가의 형제들", author: "도스토예프스키" },
      { id: 53, title: "파우스트", author: "괴테" },
      { id: 54, title: "홍루몽", author: "조설근" },
      { id: 55, title: "스완네 집 쪽으로", author: "프루스트" },
      { id: 56, title: "중용", author: "자사" },
      { id: 57, title: "토지", author: "박경리" }
    ]
  };

  const [activeTab, setActiveTab] = useState('literature');
  const [searchTerm, setSearchTerm] = useState('');

  const tabs = [
    { id: 'literature', label: '문학/수필', icon: <PenTool />, count: bookData.literature.length, color: 'amber' },
    { id: 'humanities', label: '인문/사회/철학', icon: <BookOpen />, count: bookData.humanities.length, color: 'blue' },
    { id: 'science', label: '수학/과학', icon: <Microscope />, count: bookData.science.length, color: 'emerald' },
    { id: 'university', label: '대학 권장', icon: <GraduationCap />, count: bookData.university.length, color: 'indigo' }
  ];

  const filteredBooks = useMemo(() => {
    return bookData[activeTab].filter(book => 
      book.title.toLowerCase().includes(searchTerm.toLowerCase()) ||
      book.author.toLowerCase().includes(searchTerm.toLowerCase())
    );
  }, [activeTab, searchTerm]);

  const totalBooks = Object.values(bookData).reduce((acc, curr) => acc + curr.length, 0);

  return (
    <div className="min-h-screen bg-neutral-50 text-slate-900 pb-20 font-sans">
      {/* Top Banner */}
      <div className="bg-slate-900 text-white py-14 px-6 relative overflow-hidden">
        <div className="absolute right-0 bottom-0 opacity-5 transform translate-x-1/4 translate-y-1/4">
          <Library size={400} />
        </div>
        <div className="max-w-6xl mx-auto relative z-10">
          <div className="flex items-center gap-3 mb-6">
            <div className="bg-amber-500 p-2.5 rounded-xl text-slate-900 shadow-lg shadow-amber-500/20">
              <Book className="w-6 h-6" />
            </div>
            <span className="text-amber-400 font-bold tracking-widest text-xs uppercase">Curated Reading Archive</span>
          </div>
          <h1 className="text-4xl md:text-5xl lg:text-6xl font-black mb-6 leading-tight">
            통합 도서 열람실 <br />
            <span className="text-amber-500">지식의 아카이브</span>
          </h1>
          <p className="text-slate-400 text-lg md:text-xl max-w-3xl font-medium leading-relaxed">
            명문 고등학교 및 주요 대학의 권장 도서 데이터를 바탕으로 구축된 <br />
            총 <span className="text-white border-b-2 border-amber-500 pb-1">{totalBooks}권</span>의 통합 도서 목록입니다.
          </p>
        </div>
      </div>

      {/* Main Container */}
      <div className="max-w-6xl mx-auto px-4 -mt-10">
        <div className="bg-white/80 backdrop-blur-xl rounded-[40px] shadow-2xl shadow-slate-200/50 p-6 md:p-10 mb-12 border border-white/20 sticky top-6 z-30">
          <div className="flex flex-col xl:flex-row gap-8 items-center">
            {/* Tabs Navigation */}
            <div className="flex flex-wrap justify-center gap-3 w-full xl:w-auto">
              {tabs.map((tab) => (
                <button
                  key={tab.id}
                  onClick={() => { setActiveTab(tab.id); setSearchTerm(''); }}
                  className={`group flex items-center gap-3 px-6 py-3.5 rounded-2xl text-sm font-bold transition-all duration-300 ${
                    activeTab === tab.id 
                    ? `bg-${tab.color}-600 text-white shadow-xl shadow-${tab.color}-500/20 scale-105` 
                    : 'bg-slate-100 text-slate-500 hover:bg-white hover:shadow-lg'
                  }`}
                >
                  <span className={`${activeTab === tab.id ? 'text-white' : `text-${tab.color}-500`} transition-colors`}>
                    {tab.icon}
                  </span>
                  {tab.label}
                  <span className={`ml-1 text-[10px] px-2 py-0.5 rounded-full ${activeTab === tab.id ? 'bg-white/20' : 'bg-slate-200 text-slate-500'}`}>
                    {tab.count}
                  </span>
                </button>
              ))}
            </div>

            {/* Search Bar */}
            <div className="relative flex-1 w-full">
              <div className="absolute left-6 top-1/2 -translate-y-1/2 text-slate-400">
                <Search className="w-5 h-5" />
              </div>
              <input 
                type="text" 
                placeholder="제목이나 저자를 검색해 보세요..."
                className="w-full pl-16 pr-8 py-5 bg-slate-50 border-2 border-transparent focus:bg-white focus:ring-8 focus:ring-amber-500/5 focus:border-amber-500 rounded-3xl transition-all outline-none text-slate-800 placeholder-slate-400 font-medium"
                value={searchTerm}
                onChange={(e) => setSearchTerm(e.target.value)}
              />
              {searchTerm && (
                <button 
                  onClick={() => setSearchTerm('')}
                  className="absolute right-6 top-1/2 -translate-y-1/2 text-slate-300 hover:text-slate-500 font-bold text-xs"
                >
                  초기화
                </button>
              )}
            </div>
          </div>
        </div>

        {/* Dynamic Section Header */}
        <div className="flex flex-col md:flex-row md:items-end justify-between mb-10 px-6 gap-4">
          <div>
            <div className={`text-${tabs.find(t => t.id === activeTab).color}-600 font-black text-xs tracking-[0.3em] uppercase mb-2 flex items-center gap-2`}>
              <Sparkles size={14} /> Catalog View
            </div>
            <h2 className="text-3xl font-black text-slate-800 tracking-tight">
              {tabs.find(t => t.id === activeTab).label} 리스트
            </h2>
          </div>
          <div className="bg-white shadow-sm border border-slate-200 px-6 py-2 rounded-2xl text-lg font-black text-slate-700">
            {filteredBooks.length} <span className="text-slate-300 text-sm ml-1">Books found</span>
          </div>
        </div>

        {/* Books Display Grid (Buttons Removed) */}
        {filteredBooks.length > 0 ? (
          <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
            {filteredBooks.map((book) => (
              <div 
                key={`${activeTab}-${book.id}`}
                className="group relative bg-white rounded-[40px] border border-slate-100 hover:shadow-[0_20px_40px_-10px_rgba(0,0,0,0.05)] transition-all duration-500 overflow-hidden flex flex-col p-8"
              >
                {/* Decorative Side Line */}
                <div className={`absolute left-0 top-12 bottom-12 w-1 bg-${tabs.find(t => t.id === activeTab).color}-500 rounded-r-full transform -translate-x-full group-hover:translate-x-0 transition-transform duration-500`} />
                
                <div className="flex justify-between items-start mb-8">
                  <div className={`p-4 rounded-2xl bg-slate-50 text-slate-400 group-hover:bg-${tabs.find(t => t.id === activeTab).color}-50 group-hover:text-${tabs.find(t => t.id === activeTab).color}-600 transition-all duration-300`}>
                    {tabs.find(t => t.id === activeTab).icon}
                  </div>
                  <div className="text-[10px] font-bold text-slate-300 tracking-widest bg-slate-50 px-3 py-1.5 rounded-full uppercase">
                    ID-{book.id.toString().padStart(3, '0')}
                  </div>
                </div>

                <h3 className="text-xl font-black text-slate-800 leading-tight mb-4 min-h-[3.5rem] line-clamp-2">
                  {book.title}
                </h3>
                
                <div className="flex items-center gap-3 text-slate-400 mt-auto pt-6 border-t border-slate-50">
                  <div className="w-8 h-8 rounded-full bg-slate-50 flex items-center justify-center">
                    <PenTool size={12} className="opacity-30" />
                  </div>
                  <span className="text-sm font-bold text-slate-500">{book.author}</span>
                </div>
              </div>
            ))}
          </div>
        ) : (
          <div className="py-48 text-center bg-white rounded-[60px] border-2 border-dashed border-slate-200 mx-4">
            <div className="w-28 h-28 bg-slate-50 rounded-full flex items-center justify-center mx-auto mb-10 text-slate-100">
              <Search size={56} />
            </div>
            <h3 className="text-3xl font-black text-slate-700">도서를 찾을 수 없습니다</h3>
            <p className="text-slate-400 mt-4 text-lg font-medium">검색어를 확인하거나 다른 카테고리를 선택해 주세요.</p>
          </div>
        )}
      </div>

      {/* Unified Footer */}
      <footer className="mt-40 border-t border-slate-200 py-16 px-6">
        <div className="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center gap-8">
          <div className="flex items-center gap-3 font-black text-slate-900 text-2xl tracking-tighter italic">
            <div className="bg-slate-900 text-white p-2 rounded-xl"><Library size={20} /></div>
            ELITE ARCHIVE
          </div>
          <div className="text-[11px] font-black text-slate-300 tracking-[0.3em] uppercase text-center">
            © 2024 통합 도서 열람실 프로젝트. All Books Listed based on Academic Standards.
          </div>
        </div>
      </footer>

      {/* Tailwind Utility Helper for Dynamic Classes */}
      <div className="hidden">
        <div className="bg-amber-600 shadow-amber-500/20 text-amber-500 bg-amber-50 group-hover:bg-amber-50 group-hover:text-amber-600 bg-amber-500 border-amber-500 focus:ring-amber-500/5 focus:border-amber-500 text-amber-600"></div>
        <div className="bg-blue-600 shadow-blue-500/20 text-blue-500 bg-blue-50 group-hover:bg-blue-50 group-hover:text-blue-600 bg-blue-500 border-blue-500 text-blue-600"></div>
        <div className="bg-emerald-600 shadow-emerald-500/20 text-emerald-500 bg-emerald-50 group-hover:bg-emerald-50 group-hover:text-emerald-600 bg-emerald-500 border-emerald-500 text-emerald-600"></div>
        <div className="bg-indigo-600 shadow-indigo-500/20 text-indigo-500 bg-indigo-50 group-hover:bg-indigo-50 group-hover:text-indigo-600 bg-indigo-500 border-indigo-500 text-indigo-600"></div>
      </div>
    </div>
  );
};

export default App;

```
