dev-portfolio

dev-portfolio는 웹 포트폴리오를 쉽고 빠르게 개발할 수 있도록 돕는 React 라이브러리입니다.

목차
설치
사용법
컴포넌트
Header
Channel
Channels
Intro
Skill
TechStackList
Experience
Carousel
Gallery
Masonry
Image
Item
Card
Contact
VisitorCounter
VisitorComment
ProgressBar
아이콘 입력 가이드라인
라이선스
기여자
📦 설치 (Installation)
dev-portfolio 라이브러리를 설치하는 방법은 두 가지가 있습니다.

dev-portfolio 라이브러리만 설치:

Bash

npm i dev-portfolio --save
보일러플레이트(Boiler-plate) 코드 설치:npx를 사용하여 dev-portfolio의 기본 보일러플레이트 코드를 쉽게 가져올 수 있습니다. 보일러플레이트의 README.md를 보려면 create-dev-portfolio 저장소를 방문하세요.

Bash

npx create-dev-portfolio
💡 사용법 (Usage)
dev-portfolio의 컴포넌트들을 사용하여 앱을 구성하는 방법입니다.

JavaScript

import { Header, Intro, Contact, ... } from 'dev-portfolio';

const App = () => {
  return (
    // 'dev-portfolio' 컴포넌트들을 감싸는 <div> 태그의 'className'은 반드시 'App'이어야 합니다.
    // 그래야 SideBar 컴포넌트가 id props를 인식하고 모든 컴포넌트를 SideBar에 자동으로 할당할 수 있습니다.
    <div className="App">
      <Header />
      <Intro />
      {/* ... 다른 컴포넌트들 ... */}
      <Contact />
    </div>
  );
}

export default App;
🧩 컴포넌트 (Components)
dev-portfolio 라이브러리에서 제공하는 주요 컴포넌트들입니다.

Header
내비게이션 바 역할을 하는 헤더 컴포넌트입니다.

JavaScript

import { Header } from 'dev-portfolio';

const logoOption = { /* ... */ };
const channels = [ /* ... */ ];
const sideBarOption = { /* ... */ };

const App = () => {
  return (
    <Header
      logoOption={logoOption}
      channels={channels}
      sideBarOption={sideBarOption}
      headerHeight='80px'
      headerWidth='100%'
      headerBackgroundColor='white'
    />
  );
}

export default App;
props	type	설명	기본값	참고
headerHeight	string	헤더 높이 스타일	'80px'	
headerWidth	string	헤더 너비 스타일	'100%'	
headerBackgroundColor	string	헤더 배경 색상 스타일	'white'	
logoOption	LogoOptionPropsType	로고와 타이틀 등 헤더의 속성을 커스터마이징할 수 있습니다.	"Header's Props 상세" 참조	
channels	ChannelType[]	개인 블로그, LinkedIn 등 자신을 표현하는 채널 컴포넌트의 props를 객체 배열로 입력합니다.	"Header's Props 상세" 참조	
sideBarOption	SideBarOptionPropsType	사이드바의 타이틀, 아이콘, 아이템 등의 속성을 커스터마이징할 수 있습니다.	"Header's Props 상세" 참조	

Sheets로 내보내기
Header's Props 상세
logoOption 예시

JavaScript

const logoOption = {
  redirectUrl: '/',
  logoImg: 'logo.png',
  logoHidden: false,
  title: 'dev-portfolio',
  logoMargin: '0px 16px 0px 16px',
  logoWidth: '50px',
  logoHeight: '50px',
  titleColor: 'black',
  titleSize: '24px',
  titleWeight: '800',
};
channels 예시Channels's Props 상세 섹션을 참조하세요.

sideBarOption 예시
사이드바 아이콘 변경은 iconName props를 사용하며, 아이콘 입력 가이드라인을 참조하세요.

JavaScript

const sideBarOption = {
  mainTitle: 'dev-portfolio',
  mainTitleSize: '24px',
  mainTitleColor: 'white',
  mainTitleAlign: 'left',
  mainTitleBorderColor: 'white',
  iconName: 'ant-design:menu-fold-outlined', // 가이드라인 참조
  iconSize: '28px',
  iconColor: '#434521',
  iconMargin: '0px 12px 0px 12px',
  itemTextColor: 'white',
  itemTextAlign: 'left',
  itemBackgroundColor: '#434521',
  itemHoverdBackgroundColor: 'black',
  backgroundColor: '#434521',
};
Channel
개별 소셜 미디어 또는 블로그 채널을 나타내는 컴포넌트입니다.

JavaScript

import { Channel } from 'dev-portfolio';

const App = () => {
  return (
    <Channel
      redirectUrl="https://github.com/your-username"
      name="github"
      color="black"
      size="24px"
      margin="0px 6px"
      padding="0px"
    />
  );
};

export default App;
props	type	설명	기본값	참고
redirectUrl	string	클릭 시 리디렉션될 URL	'/'	
name	string	채널 이름	'github'	
color	string	채널 아이콘 색상 스타일	'black'	
size	string	채널 아이콘 크기 스타일	'24px'	
margin	string	채널 마진 스타일	'0px 6px'	
padding	string	채널 패딩 스타일	'0px'	

Sheets로 내보내기
Channels
여러 개의 Channel 컴포넌트를 그룹화하여 표시합니다.

JavaScript

import { Channels } from 'dev-portfolio';

const channels = [ /* ... */ ];

const App = () => {
  return (
    <Channels channels={channels} />
  );
}

export default App;
props	type	설명	기본값	참고
channels	ChannelType[]	Github, LinkedIn 등 채널 전용 props 배열입니다.	"Channels's Props 상세" 참조	

Sheets로 내보내기
Channels's Props 상세
channels 예시

JavaScript

const channels = [
  {
    redirectUrl: 'https://github.com/your-username',
    name: 'github',
    color: 'black',
    size: '24px',
    margin: '0px 6px',
    padding: '0px',
  },
  {
    redirectUrl: 'https://youtube.com/your-channel',
    name: 'youtube',
    color: '#e03b35',
    size: '24px',
    margin: '0px 6px',
    padding: '0px',
  },
  {
    redirectUrl: 'https://linkedin.com/in/your-profile',
    name: 'linkedin',
    color: '#1295cd',
    size: '24px',
    margin: '0px 6px',
    padding: '0px',
  },
];
Intro
자기소개를 위한 섹션 컴포넌트입니다.

JavaScript

import { Intro } from 'dev-portfolio';

const introOption = [ /* ... */ ]; // introOption 예시는 제공되지 않았습니다.

const App = () => {
  return (
    <Intro
      id="intro-section" // Sidebar에 추가될 이름
      textAlign="left"
      backgroundColor="whitesmoke"
      title="Intro"
      shortIntro="shortIntro that will captivate people"
      description="This props name is description.\nPlease write down your brief introduction here. If you want to change the line, type backslash-n between the letters. Also you want to move the letters to the center, change textAlign to center. code your dreams!"
      titleColor="black"
      shortIntroColor="black"
      descriptionColor="black"
      descriptionBackgroundColor="white"
    />
  );
}

export default App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
textAlign	string	Intro 텍스트 정렬 스타일. 'left' 또는 'center' 중 선택 가능합니다.	'left'	
backgroundColor	string	Intro 배경 색상 스타일	'whitesmoke'	
title	string	Intro 섹션의 제목입니다.	'Intro'	
shortIntro	string	자신을 가장 잘 표현할 수 있는 메인 텍스트입니다.	'shortIntro that will captivate people'	
description	string	자기소개를 작성합니다.	'This props name is description.\nPlease write down your brief introduction here. If you want to change the line, type backslash-n between the letters. Also you want to move the letters to the center, change textAlign to center. code your dreams!'	
titleColor	string	제목 텍스트 색상 스타일	'black'	
shortIntroColor	string	ShortIntro 텍스트 색상 스타일	'black'	
descriptionColor	string	설명 텍스트 색상 스타일	'black'	
descriptionBackgroundColor	string	설명 배경 색상 스타일	'white'	

Sheets로 내보내기
Skill
개별 기술 스킬을 나타내는 컴포넌트입니다.

JavaScript

import { Skill } from 'dev-portfolio';

const App = () => {
  return (
    <Skill
      title="javascript"
      titleSize="24px"
      isHiddenTitle={false}
      iconName="ion:logo-javascript" // 가이드라인 참조
      iconSize="40px"
      iconColor="#F0DB4F"
      margin="0px"
      padding="0px"
      titleColor="black"
      borderColor="white"
      backgroundColor="white"
      borderRadius="12px"
    />
  );
};

export default App;
props	type	설명	기본값	참고
title	string	스킬을 표현하는 메인 텍스트	'javascript'	
titleSize	string	제목 크기 스타일	'24px'	
isHiddenTitle	boolean	이 값을 true로 설정하면 제목을 숨길 수 있습니다.	false	
iconName	string	다음 사이트에서 검색한 아이콘 이름을 입력하세요.	'ion:logo-javascript'	아이콘 입력 가이드라인 참조
iconSize	string	아이콘 크기 스타일	'40px'	
iconColor	string	아이콘 색상 스타일	'#F0DB4F'	
margin	string	스킬 마진 스타일	'0px'	
padding	string	스킬 패딩 스타일	'0px'	
titleColor	string	제목 색상 스타일	'black'	
borderColor	string	스킬 테두리 색상 스타일	'white'	
backgroundColor	string	스킬 배경 색상 스타일	'white'	
borderRadius	string	스킬 border-radius 스타일	'12px'	

Sheets로 내보내기
TechStackList
다양한 기술 스택과 진행률을 표시하는 리스트 컴포넌트입니다.

JavaScript

import { TechStackList } from 'dev-portfolio';

const techStackList = [ /* ... */ ];

const App = () => {
  return (
    <TechStackList
      id="tech-stack-section" // Sidebar에 추가될 이름
      gap="normal"
      techStackList={techStackList}
    />
  );
}

export default App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
gap	TechStackGapType	TechStackList 내 TechStack 사이의 간격	'normal'	
techStackList	TechStackPropsType[]	TechStack 배열입니다.	"TechStackList's Props 상세" 참조	

Sheets로 내보내기
TechStackList's Props 상세
techStackList 예시

JavaScript

const techStackList = [
  {
    nameOption: {
      name: 'Javascript',
      nameTextColor: 'black',
      logoName: 'Javascript',
      fontSize: '18px',
      logoSize: '24px',
    },
    progressBarOption: {
      rateText: '45%',
      rateTextColor: 'black',
      isHiddenRateText: false,
      backgroundColor: 'black',
      colorTo: '#E2D784',
      colorFrom: 'whitesmoke',
      width: '100%',
      height: '40px',
      animationType: 'fill-up-wave',
      isBlinking: true,
    },
  },
  {
    nameOption: {
      name: 'HTML5',
      nameTextColor: 'black',
      logoName: 'HTML-5',
      fontSize: '18px',
      logoSize: '24px'
    },
    progressBarOption: {
      rateText: '30%',
      rateTextColor: 'black',
      isHiddenRateText: false,
      backgroundColor: 'black',
      colorTo: '#E34F26',
      colorFrom: 'whitesmoke',
      width: '100%',
      height: '40px',
      animationType: 'fill-up-wave',
      isBlinking: true,
    },
  },
  {
    nameOption: {
      name: 'Nodejs',
      nameTextColor: 'black',
      logoName: 'Nodejs',
      fontSize: '18px',
      logoSize: '24px'
    },
    progressBarOption: {
      rateText: '85%',
      rateTextColor: 'black',
      isHiddenRateText: false,
      backgroundColor: 'black',
      colorTo: '#339933',
      colorFrom: 'whitesmoke',
      width: '100%',
      height: '40px',
      animationType: 'fill-up-wave',
      isBlinking: true,
    },
  },
];
gap 예시

JavaScript

// 'narrower' | 'narrow' | 'normal' | 'wide' | 'wider';
const gap = 'normal';
Experience
경력 또는 학력과 같은 경험 목록을 표시하는 컴포넌트입니다.

JavaScript

import { Experience } from 'dev-portfolio';

const historyList = [ /* ... */ ];

const App = () => {
  return (
    <Experience
      id="experience-section" // Sidebar에 추가될 이름
      title="Experience"
      textAlign="left"
      theme="basic"
      shape="square" // 'vertical' 테마에서 사용
      headerTitleColor="black"
      historyTitleColor="black"
      dateColor="black"
      descriptionColor="black"
      historyList={historyList}
    />
  );
}

export default App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
title	string	Experience 컴포넌트의 메인 타이틀 텍스트	'Experience'	
textAlign	string	Experience 텍스트 정렬	'left'	
theme	ExperienceThemeType	'basic', 'box', 'vertical' 등 다양한 테마로 경험을 꾸밀 수 있습니다.	'basic'	
shape	ExperienceVerticalOptionType	'vertical' 테마에서만 사용되는 카드 모양 ('square', 'round-square')	'square'	
headerTitleColor	string	Experience 컴포넌트의 제목 색상	'black'	
historyTitleColor	string	historyList의 제목 색상	'black'	
dateColor	string	historyList의 날짜 색상	'black'	
descriptionColor	string	historyList의 설명 색상	'black'	
historyList	ExperienceHistoryListType[]	날짜, 제목, 설명 등의 이력 데이터를 추가할 수 있습니다.	"Experience's Props 상세" 참조	

Sheets로 내보내기
Experience's Props 상세
historyList 예시

JavaScript

const historyList = [
  {
    startDate: '2022.01.01',
    endDate: '2022.03.10',
    title: 'this is title',
    description: 'This prop name is des.\nWrite down the additional explanation you want here.\nYou can break the line to backslash-n.',
  },
  {
    startDate: '2020.02',
    title: 'this is title',
    description: `If you just want to write the date and time without the text,\ndon't worry !\nYou can write a des props just by emptying it.\nAn example is shown below.`,
  },
  {
    startDate: '2018',
    endDate: '2019.12',
    title: 'this is title',
    // description을 비워두어도 됩니다.
  },
];
Carousel
이미지나 다른 컴포넌트들을 슬라이드 형태로 보여주는 캐러셀 컴포넌트입니다.

JavaScript

import { Carousel, Image } from 'dev-portfolio';

const App = () => {
  return (
    <Carousel
      id="carousel-section" // Sidebar에 추가될 이름
      width="100%"
      transition={1000} // 단위: ms
      autoplaySpeed={3000} // 단위: ms
      slideToShow={1}
      isArrowShow={true}
      isAutoplay={false}
      isAutoplayControl={true}
      arrowLocation="mid-side"
      playerLocation="bottom-mid"
      // prevArrowIcon={<MyPrevArrowIcon />} // ReactElement
      // nextArrowIcon={<MyNextArrowIcon />} // ReactElement
      // startAutoplayIcon={<MyStartIcon />} // ReactElement
      // pauseAutoplayIcon={<MyPauseIcon />} // ReactElement
    >
      {/* 여기에 사용자 정의 컴포넌트 (dev-portfolio의 Image 컴포넌트 등)를 삽입 */}
      <Image src="image1.jpg" head="프로젝트 1" />
      <Image src="image2.jpg" head="프로젝트 2" />
    </Carousel>
  );
};

export export App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
width	string	캐러셀 너비	'100%'	
transition	number	전환 애니메이션 속도	1000	단위: ms
autoplaySpeed	number	아이템이 머무는 시간	3000	단위: ms
slideToShow	number	한 번에 보여줄 아이템 개수	1	
isArrowShow	boolean	버튼 표시 여부 플래그	true	
isAutoplay	boolean	캐러셀 자동 재생 플래그	false	
isAutoplayControl	boolean	캐러셀 플레이어 표시 여부 플래그	true	
arrowLocation	ArrowLocationType	화살표 아이콘 위치	'mid-side'	
playerLocation	PlayerLocationType	재생 아이콘 위치	'bottom-mid'	
prevArrowIcon	ReactElement	이전 아이템으로 이동하는 아이콘 컴포넌트	``	
startAutoplayIcon	ReactElement	자동 재생 시작 아이콘 컴포넌트	``	

Sheets로 내보내기
Gallery
이미지 또는 아이템들을 그리드 형태로 배열하는 갤러리 컴포넌트입니다.

JavaScript

import { Gallery, Item } from 'dev-portfolio';

const App = () => {
  return (
    <Gallery
      id="gallery-section" // Sidebar에 추가될 이름
      column={3}
      gap="normal"
      theme="mid-night"
      padding="2em 10em"
    >
      {/* 여기에 사용자 정의 컴포넌트 (dev-portfolio의 Item 컴포넌트 등)를 삽입 */}
      <Item src="item1.jpg" title="작품 1" />
      <Item src="item2.jpg" title="작품 2" />
    </Gallery>
  );
};

export default App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
column	number	수직 라인의 수	3	
gap	GalleryGapType	Gallery 내 아이템 사이의 간격	'normal'	
theme	GalleryThemeType	'mid-night', 'blossom', 'fruits', 'bare-bare', 'mint-chocolate' 등 호버 시 사용자 정의 컴포넌트 색상 테마입니다.	'mid-night'	
padding	string	갤러리 패딩	'2em 10em'	

Sheets로 내보내기
Masonry
이미지 또는 아이템들을 마사리 레이아웃으로 정렬하는 컴포넌트입니다.

JavaScript

import { Masonry, Image } from 'dev-portfolio';

const App = () => {
  return (
    <Masonry
      id="masonry-section" // Sidebar에 추가될 이름
      column={4}
      padding="2em 4em"
    >
      {/* 여기에 사용자 정의 컴포넌트 (dev-portfolio의 Image 컴포넌트 등)를 삽입 */}
      <Image src="masonry1.jpg" head="이미지 1" />
      <Image src="masonry2.jpg" head="이미지 2" />
    </Masonry>
  );
};

export default App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
column	number	수직 라인의 수	4	
padding	string	Masonry 패딩	'2em 4em'	

Sheets로 내보내기
Image
이미지와 함께 제목, 부제목 등을 표시하는 컴포넌트입니다.

JavaScript

import { Image } from 'dev-portfolio';

const App = () => {
  return (
    <Image
      src="https://picsum.photos/800/600/?random"
      head="Write your head"
      headSize="20px"
      headColor="black"
      headWeight="700"
      subhead="Write your subhead"
      subheadSize="14px"
      subheadColor="black"
      redirectURL="/"
      noShowHead={false}
      zoomWhenHover={false}
    />
  );
};

export default App;
props	type	설명	기본값	참고
src	string	이미지 소스 URL		
head	string	메인 제목 텍스트	'Write your head'	
headSize	string	헤드 텍스트 크기 스타일	'20px'	
headColor	string	헤드 색상 스타일	'black'	
headWeight	string	헤드 폰트 굵기 스타일	'700'	
subhead	string	부제목 텍스트	'Write your subhead'	
subheadSize	string	부제목 텍스트 크기 스타일	'14px'	
subheadColor	string	부제목 텍스트 색상 스타일	'black'	
redirectURL	string	리디렉션될 URL	'/'	
noShowHead	boolean	텍스트 숨김 여부 플래그	false	
zoomWhenHover	boolean	아이템 호버 시 이미지 확대 여부 플래그	false	

Sheets로 내보내기
Item
갤러리 등에서 사용되는 개별 아이템 컴포넌트입니다.

JavaScript

import { Item } from 'dev-portfolio';

const App = () => {
  return (
    <Item
      src="https://picsum.photos/600/600/?random"
      title="This is title"
      description="description"
      redirectURL="/"
      textRisingSpeed={300}
      isTextRising={false}
      descriptionColor="white"
      hoverdInnerBorderColor="white"
    />
  );
};

export default App;
props	type	설명	기본값	참고
src	string	이미지 소스 URL	'https://picsum.photos/600/600/?random'	
title	string	메인 제목 텍스트	'This is title'	
description	string	설명 텍스트	'description'	
redirectURL	string	리디렉션될 URL	'/'	
textRisingSpeed	number	텍스트가 올라오는 애니메이션 속도	300	
isTextRising	boolean	텍스트 올라오는 애니메이션 적용 여부	false	
descriptionColor	string	설명 텍스트 색상 스타일	'white'	
hoverdInnerBorderColor	string	호버 시 아이템 내부 테두리 색상	'white'	

Sheets로 내보내기
Card
간단한 정보나 요소를 표시하는 카드 컴포넌트입니다.

JavaScript

import { Card } from 'dev-portfolio';

const App = () => {
  return (
    <Card
      width="10em"
      height="10em"
      redirectURL="/"
      shape="square"
      hover="none"
    >
      {/* 여기에 카드 안에 들어갈 내용 (텍스트, 이미지 등)을 넣을 수 있습니다. */}
      <h3>My Card</h3>
      <p>This is a sample card content.</p>
    </Card>
  );
};

export default App;
props	type	설명	기본값	참고
width	string	카드 너비	'10em'	
height	string	카드 높이	'10em'	
redirectURL	string	리디렉션될 URL	'/'	
shape	CardShapeType	'square', 'round-square', 'round' 등 다양한 테마로 카드의 모양을 꾸밀 수 있습니다.	'square'	
hover	CardHoverType	'up', 'down', 'zoom' 등 다양한 테마로 카드에 효과를 줄 수 있습니다.	'none'	

Sheets로 내보내기
Contact
연락처 정보 및 소셜 채널을 표시하는 컴포넌트입니다.

JavaScript

import { Contact } from 'dev-portfolio';

const channels = [ /* ... */ ];
const aboutMeInfos = [ /* ... */ ];

const App = () => {
  return (
    <Contact
      id="contact-section" // Sidebar에 추가될 이름
      backgroundColor="whitesmoke"
      title="Hello, my name is DEV_PORTFOLIO"
      titleColor="black"
      subTitle="If you're interested in me, please press the button below :D"
      subTitleColor="black"
      email="abc@dev-portfolio.com"
      buttonText="Want to work with me?"
      buttonTextColor="white"
      buttonBorderColor="black"
      channels={channels}
      aboutMeInfos={aboutMeInfos}
    />
  );
};

export default App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
backgroundColor	string	Contact 배경 색상	'whitesmoke'	
title	string	연락처 섹션의 메인 타이틀 텍스트	'Hello, my name is DEV_PORTFOLIO'	
titleColor	string	제목 색상 스타일	'black'	
subTitle	string	서브 타이틀 텍스트	'If you're interested in me, please press the button below :D'	
subTitleColor	string	서브 타이틀 텍스트 색상 스타일	'black'	
email	string	당신의 이메일 주소	'abc@dev-portfolio.com'	
buttonText	string	이메일 링크 기능을 하는 버튼 텍스트	'Want to work with me?'	
buttonTextColor	string	버튼 텍스트 색상 스타일	'white'	
buttonBorderColor	string	버튼 테두리 색상 스타일	'black'	
channels	ChannelType[]	Github, LinkedIn 등 채널 전용 props 배열입니다.	"Contact's Props 상세" 참조	
aboutMeInfos	AboutMeInfoPropsType[]	전화번호, 주소 등 개인 정보입니다.	"Contact's Props 상세" 참조	

Sheets로 내보내기
Contact's Props 상세
channels 예시

JavaScript

const channels = [
  { name: 'github', redirectUrl: 'https://', color: '#181717BB', size: '24px' },
  { name: 'naver', redirectUrl: 'https://', color: '#47A141BB', size: '24px' },
  { name: 'facebook', redirectUrl: 'https://', color: '#1877F2BB', size: '24px' },
  { name: 'youtube', redirectUrl: 'https://', color: '#FF0000BB', size: '24px' },
];
aboutMeInfos 예시

JavaScript

const aboutMeInfos = [
  { title: 'Where I live', description: 'Gangdong-gu, Seoul, Republic of Korea', },
  { title: 'Give me a call', description: 'T. +82 (0)10 1234 5678', },
  { title: 'Or, why don’t you email me?', description: 'dev-portfolio@gmail.com', },
];
VisitorCounter
방문자 수를 표시하는 컴포넌트입니다.

JavaScript

import { VisitorCounter } from 'dev-portfolio';

const App = () => {
  return (
    <VisitorCounter
      title="hits"
      theme="default"
      todayVisitor={0} // 서버에서 가져온 값
      totalVisitor={123} // 서버에서 가져온 값
      todayTitle="today"
      totalTitle="total"
      backgroundColor="#91c230c4"
      todayVisitorColor="red"
      totalVisitorColor="red"
      todayTitleColor="black"
      totalTitleColor="black"
      size="14px" // 'px' 포함 필수
    />
  );
};

export default App;
props	type	설명	기본값	참고
title	string	'default' 및 'big-size' 테마에서 사용되는 히트 제목	'hits'	
theme	VisitorCounterThemeType	방문자 카운터 테마: 'default', 'big-size', 'simple'	'default'	
todayVisitor	number	오늘의 방문자 수	0	가져온 변수 (fetched variable)
totalVisitor	number	총 방문자 수	123	가져온 변수 (fetched variable)
todayTitle	string	'big-size' 및 'simple' 테마에서 사용되는 오늘 방문자 수 제목	'today'	
totalTitle	string	'big-size' 및 'simple' 테마에서 사용되는 총 방문자 수 제목	'total'	
backgroundColor	string	todayTitle의 배경 색상	'#91c230c4'	
todayVisitorColor	string	오늘 방문자 수 색상 스타일	'red'	
totalVisitorColor	string	총 방문자 수 색상 스타일	'red'	
todayTitleColor	string	오늘 제목 색상 스타일	'black'	
totalTitleColor	string	총 제목 색상 스타일	'black'	
size	string	방문자 카운터 컴포넌트의 폰트 크기 및 컴포넌트 크기	'14px'	'px' 포함 필수

Sheets로 내보내기
VisitorCounter's Props 상세
theme 예시

JavaScript

// 'default' | 'big-size' | 'simple'
const theme = 'default';
VisitorCounter 예시 (props 구조는 이미 위의 표에 자세히 설명되어 있습니다.)

JavaScript

const visitorCounter = {
  title: 'hits',
  todayTitle: 'today',
  totalTitle: 'total',
};
VisitorComment
방문자가 댓글을 남길 수 있는 방명록 컴포넌트입니다.

JavaScript

import { VisitorComment } from 'dev-portfolio';

const commentList = [ /* ... */ ]; // 서버에서 가져온 데이터
const App = () => {
  // 실제 애플리케이션에서는 useState 등을 사용하여 comment, nickname, password를 관리합니다.
  const [comment, setComment] = useState('');
  const [nickname, setNickname] = useState('');
  const [password, setPassword] = useState('');

  const handleCreateComment = () => { /* 댓글 생성 로직 */ };
  const handleChangeDescription = (e) => setComment(e.target.value);
  const handleChangeNickname = (e) => setNickname(e.target.value);
  const handleChangePassword = (e) => setPassword(e.target.value);

  return (
    <VisitorComment
      id="visitor-comment-section" // Sidebar에 추가될 이름
      theme="basic"
      backgroundColor="whitesmoke"
      inputBackgroundColor="White"
      inputFontColor="Black"
      inputPlacehoderColor="Black"
      userInputLineColor="#b4b4b4a2"
      buttonColor="#1877f"
      listBackgroundColor="white"
      listCommentColor="black"
      listNicknameColor="#959595"
      listDateColor="#959595"
      progressbarColor="#5f5f5f"
      isShowScrollDownIcon={true}
      scrollDownIconColor="black"
      descriptionPlaceholder="write your description..."
      nicknamePlaceholder="ID"
      passwordPlaceholder="PW"
      commentList={commentList} // 서버에서 가져온 데이터
      comment={comment}
      nickname={nickname}
      password={password}
      handleCreateComment={handleCreateComment}
      handleChangeDescription={handleChangeDescription}
      handleChangeNickname={handleChangeNickname}
      handleChangePassword={handleChangePassword}
    />
  );
}

export default App;
props	type	설명	기본값	참고
id	string	Sidebar에 추가될 이름		아이콘 입력 가이드라인 참조
theme	VisitorCommentThemeType	방문자 댓글 테마: 'basic', 'box', 'vertical'	'basic'	
backgroundColor	string	VisitorComment 배경 색상	'whitesmoke'	
inputBackgroundColor	string	방명록 작성 칸의 배경 색상	'White'	
inputFontColor	string	댓글, 사용자 정보 입력란의 폰트 색상	'Black'	
inputPlacehoderColor	string	댓글, 사용자 정보 입력란의 플레이스홀더 폰트 색상	'Black'	
userInputLineColor	string	사용자 정보 필드의 밑줄 색상	'#b4b4b4a2'	
buttonColor	string	전송 버튼의 폰트 색상	'#1877f'	
listBackgroundColor	string	댓글 목록의 배경 색상	'white'	
listCommentColor	string	댓글 목록에서 댓글의 색상	'black'	
listNicknameColor	string	댓글 목록에서 닉네임의 색상	'#959595'	
listDateColor	string	댓글 목록에서 날짜의 색상	'#959595'	
progressbarColor	string	스크롤 이벤트 발생 시 생성되는 진행 바의 색상	'#5f5f5f'	
isShowScrollDownIcon	boolean	스크롤 이벤트 발생 시 아이콘 표시 여부	true	
scrollDownIconColor	string	ScrollDown 아이콘의 색상	'black'	isShowScrollDownIcon이 true일 때만 작동
descriptionPlaceholder	string	설명 영역의 플레이스홀더	'write your description...'	
nicknamePlaceholder	string	닉네임 영역의 플레이스홀더	'ID'	
passwordPlaceholder	string	비밀번호 영역의 플레이스홀더	'PW'	
commentList	VisitorCommentListType	설명, 닉네임, 날짜와 같은 댓글 목록입니다.	"VisitorComment's Props 상세" 참조	가져온 변수 (fetched variable)
comment	string	댓글 입력란에 입력한 데이터를 이 props에 넣어주세요. 서버로 HTTP 요청을 보내 DB에 저장됩니다.	'this portfolio is very nice'	댓글 입력란에 입력된 데이터
nickname	string	닉네임 입력란에 입력한 데이터를 이 props에 넣어주세요. 서버로 HTTP 요청을 보내 DB에 저장됩니다.	'dev-portfolio'	닉네임 입력란에 입력된 데이터
password	string	비밀번호 입력란에 입력한 데이터를 이 props에 넣어주세요. 서버로 HTTP 요청을 보내 DB에 저장됩니다.	'1234'	비밀번호 입력란에 입력된 데이터
handleCreateComment	(e?: React.MouseEvent) => void	댓글 생성 이벤트 핸들링을 위한 Props		
handleChangeDescription	(e?: React.ChangeEvent) => void	설명 변경 이벤트 핸들링을 위한 Props		
handleChangeNickname	(e?: React.ChangeEvent) => void	닉네임 변경 이벤트 핸들링을 위한 Props		
handleChangePassword	(e?: React.ChangeEvent) => void	비밀번호 변경 이벤트 핸들링을 위한 Props		

Sheets로 내보내기
VisitorComment's Props 상세
commentList 예시
설명, 닉네임, 날짜와 같은 댓글 목록입니다. 이 props는 백엔드에서 가져온 데이터입니다.

JavaScript

const commentList = [
  {
    description: `The scroll customization method is the same as the teckstack component progress bar, so please use it!`,
    nickname: 'woorim960',
    date: '2022-08-26',
  },
  {
    description: `Progress bar customization is also possible when creating a scroll.`,
    nickname: 'seohyunsim',
    date: '2022-08-26',
  },
  {
    description: `Likewise, there are three types of themes: basic, box, and vertical.`,
    nickname: 'jisu3817',
    date: '2022-08-26',
  },
  {
    description: 'Refer to dev-portfolio README.md for instructions on building a personal server.',
    nickname: 'soonki-98',
    date: '2022-08-26',
  },
  {
    description: `A personal server can be built through environmental variables, and visitors can write their text and nicknames.`,
    nickname: 'woorim960',
    date: '2022-08-26',
  },
  {
    description: 'By looking at your portfolio, visitors can leave a guest book.',
    nickname: 'seohyunsim',
    date: '2022-08-26',
  },
];
ProgressBar
JavaScript

import { ProgressBar } from 'dev-portfolio';

const App = () => {
  return (
    <ProgressBar
      rateText="75%"
      rateTextColor="blue"
      isHiddenRateText={false}
      backgroundColor="lightgray"
      colorTo="green"
      colorFrom="lightgreen"
      width="100%"
      height="20px"
      animationType="fill-up-wave"
      isBlinking={true}
    />
  );
};

export default App;
props	type	설명	기본값	참고
rateText	string	진행률 텍스트	''	유추값
rateTextColor	string	진행률 텍스트 색상	'black'	유추값
isHiddenRateText	boolean	진행률 텍스트 숨김 여부	false	유추값
backgroundColor	string	배경 색상	'lightgray'	유추값
colorTo	string	진행률이 채워지는 색상 (종료)	'blue'	유추값
colorFrom	string	진행률이 채워지는 색상 (시작)	'lightblue'	유추값
width	string	너비	'100%'	유추값
height	string	높이	'10px'	유추값
animationType	string	애니메이션 타입 (예: 'fill-up-wave')	''	유추값
isBlinking	boolean	깜빡임 효과 여부	false	유추값
