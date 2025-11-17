## 문제 상황
시나리오 챌린지: 의견 조율을 위한 신속한 웹 프로토타입 개발
1. 가상 문제 상황
페르소나: 멀티미디어 콘텐츠 기업 '네오스트림'의 프론트엔드 개발자 (3년 차)
- 배경:
귀사의 콘텐츠 운영팀으로부터 "사내 영상 리뷰 및 승인용 웹 대시보드" 제작을 긴급하게 요청받았습니다.
현재 기획서가 완성되지 않은 상태이며, 기획팀은 "직관적인 UI", 디자인팀은 "트렌디한 다크 모드", 운영팀은 "데이터 밀집형 테이블"을 각각 주장하며 의견이 좁혀지지 않고 있습니다.
- 핵심 문제:
말로만 회의를 진행하다 보니 서로 상상하는 결과물이 달라 의사결정이 지연되고 있습니다.
오늘 오후 4시 회의 전까지, 실제로 작동하는 형태의 결과물이 없으면 프로젝트 착수가 무기한 연기될 위기입니다.
디자인 툴(Figma 등)로 그리기에는 시간이 부족하고, 버튼 클릭 등 인터랙션이 가능한 HTML/CSS 기반의 퍼블리싱 결과물을 보여줘야만 이해관계자들을 설득할 수 있습니다.
- 해결 과제:
요구사항(영상 플레이어 영역, 타임스탬프 댓글 기능, 승인/반려 버튼, 다크 모드 스타일)을 포함한 단일 페이지 웹 프로토타입 코드(HTML, CSS, JS)를 AI를 통해 즉시 생성하십시오.
이 코드는 회의 시간 내에 즉석에서 수정 요청을 반영할 수 있을 만큼 구조가 명확해야 합니다.
2. 훈련 초점 (힌트)
이 문제는 [코딩 및 프로토타입 생성 / 시각화] 능력을 평가
단순한 텍스트 생성이 아니라, 구체적인 UI/UX 요구사항을 구조화된 언어(코드)로 변환하는 프롬프트 엔지니어링 기술이 필요
---
## 프롬프트 유형 및 선택 이유
| 구분 | 내용 |
| :--- | :--- |
| 프롬프트 유형 | 코드 생성 (Code Generation) 및 조건부 프로토타이핑 (Conditional Prototyping) |
| 선택 이유 | 단순한 설명이나 구조화된 텍스트가 아닌, 실제로 작동(버튼 클릭, 다크 모드 등)하고 시각적인 디자인/기능 제약 조건을 만족시키는 단일 파일 웹 애플리케이션(HTML/CSS/JS) 생성이 핵심 목표입니다. 이는 AI의 코딩 능력을 극대화하여 실제 개발 시간을 대체하는 훈련입니다. |

## 문제 해결 프롬프트 작성을 위해 추가로 필요한 요건
| 요건 | 설명 및 구체화 |
| :--- | :--- |
| 개발 환경 설정 | 단일 HTML 파일 내에 CSS(Tailwind CSS 필수)와 JavaScript를 모두 포함할 것을 명시하여 신속한 배포 및 수정 환경을 구축합니다. |
| 디자인 요구사항 반영 | 디자인팀의 요청인 '트렌디한 다크 모드'와 기획팀의 '직관적인 UI'를 충족하기 위해, Tailwind CSS 사용과 함께 어둡고 세련된 색상 팔레트(`bg-gray-900`)를 지정합니다. |
| 기능 요구사항 구체화 | 핵심 기능 4가지(① 영상 영역, ② 타임스탬프 댓글, ③ 승인/반려 버튼, ④ 데이터 밀집형 테이블)를 UI 컴포넌트로 명확하게 구분하여 구조화합니다. |
| 인터랙션 명시 | 특히 '타임스탬프 댓글 기능'과 '승인/반려 버튼 상태 변경'을 구현하도록 요청하여 프로토타입의 핵심 목적인 '작동하는 결과물'을 확보합니다. |
| 페르소나 강화 | '네오스트림 프론트엔드 개발자'로서의 신속함과 전문성을 반영하여, 구조가 명확하고 쉽게 수정 가능한 코드를 요구합니다. |

## 최종 문제 해결 프롬프트
```
역할: 당신은 멀티미디어 콘텐츠 기업 '네오스트림'의 프론트엔드 개발자이며, 긴급 회의를 위한 프로토타입 제작을 맡았습니다.

목표: 기획, 디자인, 운영팀의 상충되는 요구사항을 즉시 시각화하여 의견을 조율할 수 있는 단일 페이지 웹 프로토타입(HTML) 코드를 생성하십시오.

핵심 요구사항 (모두 충족해야 함):
1.  기술 스택: 단일 파일 HTML로 구현하며, CSS는 Tailwind CSS (다크 모드 필수)를 사용하고, 모든 JavaScript 코드는 `<script>` 태그 내에 포함합니다.
2.  디자인: 전체적인 테마는 '트렌디한 다크 모드' (어두운 배경, 밝은 강조색)로 설정하고, 모든 요소는 직관적이고 모바일 대응이 가능한 레이아웃을 따릅니다.
3.  UI 구성: 화면을 크게 좌측(영상 영역)과 우측(댓글/컨트롤)으로 나누고 하단에 테이블을 배치합니다.
    * 영역 A (좌측): 영상 플레이어 영역 (Placeholder 사용 가능)
    * 영역 B (좌측 하단): 영상 승인(Approve) 및 반려(Reject) 버튼. 버튼 클릭 시 상단의 상태 표시기가 '대기 중'에서 해당 상태로 변경되는 인터랙션을 구현합니다.
    * 영역 C (우측): 타임스탬프 댓글 리스트 및 입력창. 댓글 입력 시 현재 Mock 비디오 시간(예:)이 자동으로 붙여져 리스트에 추가되는 인터랙션을 구현합니다.
    * 영역 D (하단): 운영팀의 요구사항을 반영한 데이터 밀집형 리뷰 현황 테이블 (Mock 데이터 3줄 이상 포함).

출력 형식: 모든 코드는 하나의 `html` 파일 블록으로만 출력하십시오.
```
---

##  문제 해결 프롬프트 실행 결과: 60초 숏폼 대본 (JSON)

<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>사내 영상 리뷰 및 승인 대시보드 프로토타입</title>
    <!-- Tailwind CSS CDN 로드 -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <style>
        /* 기본 다크 모드 배경 및 Inter 폰트 설정 */
        body {
            font-family: 'Inter', sans-serif;
        }
        /* 스크롤바 스타일링 */
        .custom-scrollbar::-webkit-scrollbar {
            width: 8px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background-color: #4b5563; /* gray-600 */
            border-radius: 10px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background-color: #1f2937; /* gray-800 */
        }
    </style>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        'neo-primary': '#4f46e5', // Indigo-600
                        'neo-accent': '#10b981',  // Emerald-500
                    }
                }
            }
        }
    </script>
</head>
<body class="dark bg-gray-900 text-white min-h-screen p-4 sm:p-8">

    <!-- 메인 대시보드 컨테이너 -->
    <div class="max-w-7xl mx-auto space-y-8">
        <header class="pb-4 border-b border-gray-700">
            <h1 class="text-3xl font-extrabold text-white">영상 리뷰 & 승인 대시보드 (프로토타입)</h1>
            <p class="text-gray-400">의견 조율을 위한 인터랙티브 프로토타입</p>
        </header>

        <!-- 메인 콘텐츠 영역: 비디오 플레이어 + 댓글/상태 -->
        <div class="lg:flex lg:space-x-8 space-y-8 lg:space-y-0">
            
            <!-- A. 영상 플레이어 및 승인 컨트롤 (좌측) -->
            <div class="lg:w-2/3 space-y-6">
                
                <!-- 비디오 플레이어 영역 -->
                <div class="aspect-video bg-black rounded-xl shadow-2xl overflow-hidden relative">
                    <!-- 실제 영상 대신 Placeholder 사용 -->
                    <div class="flex items-center justify-center h-full text-gray-400 text-xl">
                        [PLACEHOLDER] 영상 플레이어 영역
                    </div>
                    <!-- Mock Playback Control -->
                    <div class="absolute bottom-0 left-0 right-0 p-2 bg-gray-800/80 text-sm flex items-center justify-between">
                        <span id="current-time">00:00</span> / <span>02:30</span>
                        <svg id="play-pause" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 cursor-pointer text-neo-primary hover:text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.752 11.168l-3.197 2.132A1 1 0 0010 14.288v-4.576a1 1 0 001.555-.832l3.197 2.132a1 1 0 010 1.664z" />
                          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                        </svg>
                    </div>
                </div>

                <!-- 승인/반려 버튼 -->
                <div class="bg-gray-800 p-4 rounded-xl shadow-lg flex flex-col sm:flex-row justify-between items-center space-y-4 sm:space-y-0 sm:space-x-4">
                    <div class="text-lg font-semibold w-full sm:w-auto">
                        현재 상태: <span id="review-status" class="text-yellow-400">대기 중</span>
                    </div>
                    <div class="flex space-x-4 w-full sm:w-auto">
                        <button id="btn-approve" class="flex-1 px-6 py-3 bg-neo-accent text-white font-bold rounded-lg shadow-md hover:bg-emerald-600 transition duration-150">
                            승인 (Approve)
                        </button>
                        <button id="btn-reject" class="flex-1 px-6 py-3 bg-red-600 text-white font-bold rounded-lg shadow-md hover:bg-red-700 transition duration-150">
                            반려 (Reject)
                        </button>
                    </div>
                </div>

            </div>

            <!-- B. 타임스탬프 댓글 및 리뷰 테이블 (우측) -->
            <div class="lg:w-1/3 space-y-6">

                <!-- 타임스탬프 댓글 기능 -->
                <div class="bg-gray-800 p-4 rounded-xl shadow-lg">
                    <h2 class="text-xl font-bold mb-3 text-neo-primary">타임스탬프 의견</h2>
                    <div class="flex space-x-2 mb-3">
                        <input type="text" id="comment-input" placeholder="여기에 의견을 입력하세요..." class="w-full p-2 rounded-md bg-gray-700 border border-gray-600 text-white focus:ring-neo-primary focus:border-neo-primary" />
                        <button id="btn-add-comment" class="flex-shrink-0 px-4 py-2 bg-neo-primary text-white font-semibold rounded-md hover:bg-indigo-700 transition duration-150">
                            댓글 추가
                        </button>
                    </div>
                    
                    <!-- 댓글 리스트 영역 -->
                    <div id="comments-list" class="space-y-3 h-56 custom-scrollbar overflow-y-auto pr-2">
                        <!-- 초기 Mock 댓글 -->
                        <div class="bg-gray-700 p-3 rounded-lg text-sm">
                            <span class="text-neo-accent font-mono mr-2">[00:15]</span>
                            <span class="text-gray-300">인트로 음악이 너무 잔잔합니다. 좀 더 후킹하게 변경 요청합니다.</span>
                            <span class="block text-right text-xs text-gray-500">- 기획팀 김**</span>
                        </div>
                        <div class="bg-gray-700 p-3 rounded-lg text-sm">
                            <span class="text-neo-accent font-mono mr-2">[01:02]</span>
                            <span class="text-gray-300">이 부분의 자막 폰트 크기를 조금 키워야 할 것 같습니다.</span>
                            <span class="block text-right text-xs text-gray-500">- 디자인팀 박**</span>
                        </div>
                    </div>
                </div>

            </div>
        </div>

        <!-- C. 데이터 밀집형 리뷰 상태 테이블 (하단 - 운영팀 요구사항) -->
        <div class="bg-gray-800 p-6 rounded-xl shadow-lg">
            <h2 class="text-2xl font-bold mb-4 text-neo-primary">영상 리뷰 상세 현황 (데이터 밀집형)</h2>
            <div class="overflow-x-auto custom-scrollbar">
                <table class="min-w-full table-auto border-separate border-spacing-y-2">
                    <thead class="bg-gray-700">
                        <tr class="text-sm text-gray-300 uppercase">
                            <th class="p-3 text-left rounded-tl-lg">버전</th>
                            <th class="p-3 text-left">검토자</th>
                            <th class="p-3 text-left">타임코드</th>
                            <th class="p-3 text-left">주요 의견</th>
                            <th class="p-3 text-left">소요 시간</th>
                            <th class="p-3 text-left rounded-tr-lg">상태</th>
                        </tr>
                    </thead>
                    <tbody class="text-sm">
                        <!-- Mock Data 1 -->
                        <tr class="bg-gray-700/50 hover:bg-gray-700 transition duration-150 rounded-lg">
                            <td class="p-3 font-mono rounded-l-lg">V1.1</td>
                            <td class="p-3">김태현(기획)</td>
                            <td class="p-3">00:15</td>
                            <td class="p-3">음악 톤 변경</td>
                            <td class="p-3 text-yellow-400">10h 30m</td>
                            <td class="p-3 rounded-r-lg"><span class="bg-yellow-600/20 text-yellow-400 py-1 px-2 text-xs font-medium rounded-full">대기</span></td>
                        </tr>
                        <!-- Mock Data 2 -->
                        <tr class="bg-gray-700/50 hover:bg-gray-700 transition duration-150 rounded-lg">
                            <td class="p-3 font-mono rounded-l-lg">V1.0</td>
                            <td class="p-3">이서연(운영)</td>
                            <td class="p-3">전체</td>
                            <td class="p-3">데이터 확인 완료</td>
                            <td class="p-3 text-neo-accent">1h 12m</td>
                            <td class="p-3 rounded-r-lg"><span class="bg-neo-accent/20 text-neo-accent py-1 px-2 text-xs font-medium rounded-full">승인</span></td>
                        </tr>
                        <!-- Mock Data 3 -->
                        <tr class="bg-gray-700/50 hover:bg-gray-700 transition duration-150 rounded-lg">
                            <td class="p-3 font-mono rounded-l-lg">V1.2</td>
                            <td class="p-3">박지민(디자인)</td>
                            <td class="p-3">01:02</td>
                            <td class="p-3">자막 크기 수정</td>
                            <td class="p-3 text-red-400">0h 50m</td>
                            <td class="p-3 rounded-r-lg"><span class="bg-red-600/20 text-red-400 py-1 px-2 text-xs font-medium rounded-full">반려</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>

    </div>

    <!-- JavaScript for Interactivity -->
    <script>
        // DOM 요소 가져오기
        const statusEl = document.getElementById('review-status');
        const btnApprove = document.getElementById('btn-approve');
        const btnReject = document.getElementById('btn-reject');
        const commentInput = document.getElementById('comment-input');
        const btnAddComment = document.getElementById('btn-add-comment');
        const commentsList = document.getElementById('comments-list');
        const currentTimeEl = document.getElementById('current-time');

        // 1. Mock Video Time Logic
        let mockTimeSeconds = 0;
        const totalDurationSeconds = 150; // 02:30

        // 시간을 MM:SS 형식으로 포맷하는 함수
        function formatTime(totalSeconds) {
            const minutes = Math.floor(totalSeconds / 60);
            const seconds = Math.floor(totalSeconds % 60);
            return `${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;
        }

        // 현재 시간을 5초 간격으로 업데이트 (시뮬레이션)
        setInterval(() => {
            mockTimeSeconds = (mockTimeSeconds + 5) % totalDurationSeconds;
            currentTimeEl.textContent = formatTime(mockTimeSeconds);
        }, 1000); // 1초에 5초 진행되는 척 시뮬레이션

        // 2. 승인/반려 버튼 로직
        function setStatus(status, colorClass) {
            statusEl.textContent = status;
            statusEl.className = `text-${colorClass}`;
        }

        btnApprove.addEventListener('click', () => {
            setStatus('승인 완료', 'neo-accent');
            console.log('프로토타입: 영상이 최종 승인되었습니다.');
        });

        btnReject.addEventListener('click', () => {
            setStatus('반려됨 (수정 필요)', 'red-400');
            console.log('프로토타입: 영상이 반려되었습니다.');
        });

        // 3. 타임스탬프 댓글 로직
        btnAddComment.addEventListener('click', () => {
            const commentText = commentInput.value.trim();
            if (commentText === "") {
                // 경고창 대신 인라인 메시지 사용
                alert('댓글 내용을 입력해주세요.');
                return;
            }

            const timestamp = formatTime(mockTimeSeconds);
            
            // 새 댓글 요소 생성
            const newComment = document.createElement('div');
            newComment.className = 'bg-gray-700 p-3 rounded-lg text-sm opacity-0 transition-opacity duration-300';
            
            // 임의의 사용자 이름 설정
            const mockUser = ['PD 김**', '운영팀 박**', '기획팀 이**'][Math.floor(Math.random() * 3)];

            newComment.innerHTML = `
                <span class="text-neo-accent font-mono mr-2">[${timestamp}]</span>
                <span class="text-gray-300">${commentText}</span>
                <span class="block text-right text-xs text-gray-500">- ${mockUser}</span>
            `;

            // 목록 맨 위에 새 댓글 추가 (최신순)
            commentsList.prepend(newComment);
            
            // 애니메이션 효과 적용
            setTimeout(() => newComment.classList.remove('opacity-0'), 10);
            
            // 입력 필드 초기화
            commentInput.value = '';
            
            // 스크롤 맨 위로 이동
            commentsList.scrollTop = 0;
        });

        // 엔터 키로 댓글 추가 기능 활성화
        commentInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                btnAddComment.click();
            }
        });

        // 경고창 대신 alert()을 대체하는 간단한 함수 (프로토타입 용도)
        function alert(message) {
            const existingAlert = document.getElementById('custom-alert');
            if (existingAlert) existingAlert.remove();
            
            const alertDiv = document.createElement('div');
            alertDiv.id = 'custom-alert';
            alertDiv.className = 'fixed top-4 right-4 bg-yellow-500 text-gray-900 p-4 rounded-lg shadow-xl z-50 transition-opacity duration-300';
            alertDiv.textContent = message;

            document.body.appendChild(alertDiv);

            setTimeout(() => {
                alertDiv.style.opacity = '0';
                setTimeout(() => alertDiv.remove(), 300);
            }, 3000);
        }

    </script>
</body>
</html>