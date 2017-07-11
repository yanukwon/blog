---
layout: page
title: OpenFOAM test
author: Woensug Eric Choi
---

<p style="TEXT-ALIGN: center"><a class="tx-link" style="FONT-SIZE: 12px; LINE-HEIGHT: 36px" href="http://www.geocities.jp/penguinitis2002/study/OpenFOAM/OpenFOAM-info.html" target="_blank">일본어 원문링크</a></p>
<p style="TEXT-ALIGN: center"><span style="FONT-SIZE: 9pt; LINE-HEIGHT: 6px">작성일 : 2015년 10월 29일<br />번역일 : 2016년 &nbsp;&nbsp;1월 28</span><span style="font-size: 9pt; line-height: 6px;">일</span></p>
<p style="TEXT-ALIGN: center"><span style="font-size: 9pt; line-height: 6px;">갱신일 : 2016년 &nbsp; 3월 30</span><span style="font-size: 9pt; line-height: 6px;">일</span></p><div><span style="font-size: 9pt; line-height: 6px;"><br /></span></div><p style="margin-top: 0px; margin-bottom: 0px; text-align: center;"><span style="font-size: 9pt; line-height: 6px;"><br /></span></p>
<p style="margin-top: 0px; margin-bottom: 0px; text-align: center;"><span style="color: rgb(107, 153, 0);">크롬 브라우저로 보시는 것을 권장해 드립니다.</span></p>
<p style="margin-top: 0px; margin-bottom: 0px; text-align: center;"><br class="Apple-interchange-newline"><br /></p><div><p style="margin-top: 0px; margin-bottom: 0px; text-align: center;"><span style="font-size: 16px; line-height: 38.4px;"><br class="Apple-interchange-newline">&nbsp;----- OpenFOAM 소스코드를 다루는 문법 기본&nbsp;----</span><span style="line-height: 2.4; font-size: 16px;">-</span></p><div style="text-align: center;"><p style="margin-top: 0px; margin-bottom: 0px;"><span style="font-size: 12pt; line-height: 2.4;"><a href="http://onedayof.tistory.com/entry/OpenFOAM-%EA%B8%B0%EB%B3%B8-OpenFOAM-%EB%AC%B8%EB%B2%95-%EA%B8%B0%EB%B3%B8" target="_blank" class="tx-link">OpenFOAM 소스코드를 다루는 문법 기본으로&nbsp;이동</a></span></p>
<p style="margin-top: 0px; margin-bottom: 0px;"><span style="font-size: 16px; line-height: 38.4px;">&nbsp;------------------------------------------------------------</span></p></div><div style="font-size: 16px; line-height: 2.4; text-align: center;"><span style="line-height: 2.4;">&nbsp;------ OpenFOAM 배경이론 간단정리 시리즈 ------</span></div><div style="text-align: center;"><p style="margin-top: 0px; margin-bottom: 0px;"><span style="font-size: 12pt; line-height: 2.4;"><a href="http://onedayof.tistory.com/82" target="_blank" class="tx-link">OpenFOAM 배경이론 간단정리 목차로 이동</a></span></p>
<p style="margin-top: 0px; margin-bottom: 0px;"><span style="font-size: 16px; line-height: 38.4px;">&nbsp;------------------------------------------------------------</span></p></div></div><div style="font-size: 16px; line-height: 2.4; text-align: center;"><span style="line-height: 2.4;">&nbsp;------ OpenFOAM 소스코드 파해치기 시리즈 ------</span></div><div style="text-align: center;"><p style="margin-top: 0px; margin-bottom: 0px;"><span style="font-size: 12pt; line-height: 2.4;"><a href="http://onedayof.tistory.com/entry/OpenFOAM-%EC%86%8C%EC%8A%A4%EC%BD%94%EB%93%9C-%ED%8C%8C%ED%95%B4%EC%B9%98%EA%B8%B0-%EC%8B%9C%EB%A6%AC%EC%A6%88" target="_blank" class="tx-link">OpenFOAM 소스코드 파해치기 목차로 이동</a></span></p>
<p style="margin-top: 0px; margin-bottom: 0px;"><span style="font-size: 16px; line-height: 38.4px;">&nbsp;------------------------------------------------------------</span></p></div>
<p style="TEXT-ALIGN: center; LINE-HEIGHT: 0.8"><span style="LINE-HEIGHT: 6px"><br /></span></p>
<p style="TEXT-ALIGN: center; LINE-HEIGHT: 0.8"><br /></p>
<div>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 들어가기&nbsp;</span></strong></td></tr></tbody></table></p>
<p><span style="FONT-SIZE: 12pt; LINE-HEIGHT: 1.5">OpenFOAM을 시작해 보려는&nbsp;분들을 위한 오픈폼 정보</span></p>
<p>&nbsp;</p></div>
<div>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; OpenFOAM이란?&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">OpenFOAM(Open source Field Operation And Manipulation, 오픈폼)은 GNU General Public License (GPL)을 기반으로하는 오픈소스 전산유체해석(Computational Fluid Dynamics:CFD) 툴킷이다. 객체지향프로그래밍 언어 C++로 개발된 편미분방정식 솔버개발용 클래스 라이브러리이며 C++의 문법을 활용해 높은 가독성과 확장성을 제공한다. 예를들면 스칼라수송방정식을 계산하는 코드의 경우 다음과 같이 기술 가능하다.</span></p>
<p style="LINE-HEIGHT: 0.5"><br /></p><pre class="prettyprint linenums:0">Solve
(
    fem::ddt(T)
  + fvm::div(phi, T)
  - fvm::laplacian(DT, T)
);</pre>
<p style="LINE-HEIGHT: 0.5"><br /></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">이와 같이, 전산유체역학의 지식을 숙지했다면 코드를 보고 대략적인 의미를 파악할수 있으며&nbsp;유체장(field)의 방정식을 푸는 솔버도 익숙한 표현으로 기술된다.</span></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">또한, 오픈폼은 위에서 말한 클래스 라이브러리를 이용해 작성된 표준 솔버, 유틸리티 툴이 다수 내장되어 있다. 표준솔버중에는 경우에 따라 바로 사용가능한 수준의 것도 포함되어 있다. </span></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">원래 영국의 Imperial College에서 개발된 것을 Nabla사가 "FOAM"이라는 이름으로 판매했던 것을 2004년 OpenCFD사가 "OpenFOAM"이라는 오픈소스로 공개하였다. 2011년 8월 OpenCFD사는 Silicon Graphics사(SGI)에 인수되었으나 OpenFOAM은 비영리단체 OpenFOAM Foundation에서 계속해 오픈소스로서 공개하도록 되었다. 2012년 9월 OpenCFD사는 또한번 ESI Group에 인수된다. "OpenFOAM"은 OpenCFD사에 상표등록되어 있다</span><span style="font-size: 12pt; line-height: 2.4;">.</span></p>
<p style="line-height: 0.2;"></p>
<p style="line-height: 2.4;"><span style="font-size: 12pt;">2015 년 3월, OpenFOAM의(더 정확히는 FOAM의)&nbsp;창시자인 Henry Weller는 OpenCFD사에서 나와 CFD Direct라는 회사를 차려 &nbsp;OpenFOAM Foundation/OpenFOAM 프로젝트 멤버의 입장에서 OepnFOAM의 개발을 진행중인 듯 하다</span><span style="font-size: 12pt; line-height: 2.4;">.</span></p>
<p style="line-height: 0.2;"></p>
<p style="line-height: 2.4;"><span style="font-size: 12pt;">2016년 현재, OpenFOAM의 권리보유자에 의한 "공식적" 인 배포는 OpenFOAM Foundation에 의한 OpenFOAM과, OpenCFD 사 (ESI)에 의한 OpenFOAM+ 가 있다. 이것에 대해 CFD Online에서 논의되고 있다.&nbsp;(<a href="http://www.cfd-online.com/Forums/openfoam/165322-openfoam-v3-0-a.html" target="_blank" class="tx-link">OpenFOAM v3.0+ ??</a>). OpenFOAM을 RHEL 이라고한다면 OpenFOAM+ 은 Fedora 와 같은 개념인가? (반대인가?)</span></p>
<p style="line-height: 2.4;"><br /></p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 2.4"></p>
<div>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 오픈폼에 대한 착각&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈폼은 통상 말하는 유체해석솔버와 다르며, 유한체적법을 중심으로하는 편미분방정식 솔버 개발용 클래스 라이브러리와, 그것을 이용해 작성된 몇가지의 솔버와 유틸리티 툴 묶음이다. 일반적인 상용프로그램의 경우 필요한 기능을 활성화시키기 위해 버튼을 누르기만 하면 되는것과 달리 필요한 기능을 가지는 솔버를 제공되는 표준솔버 중에서 선택하게 된다. 유저가 필요로 하는 기능을 가지는 솔버가 존재하지 않는 경우 직접 솔버를 개발할 필요가 있다. 어떤의미로는 상당한 지식과 시간, 경우에 따라서는 재정을 필요로 하게 된다.</span></p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 2.4"></p>
<div>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 무엇을 할 수 있는가&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">표준 솔버의 범위에서 아래와 같은 것이 가능하다.</span></p>
<ul style="LIST-STYLE-TYPE: square">
<li>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">비압축성유체의 정상/비정상난류해석</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">압축성유체의 정상/비정상열대류해석</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">유체,고체열전도(CHT)해석</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">다상유동해석(경계면추적법/다상유체모델)</span></p></li></ul>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">이 외에도 일반적이진 않은 연소모델을 이용한 연소해석솔버, 아음속 및 초음속을 포함하는 압축성유체솔버 등이 있다. 입자계산도 가능은 하나 현재 일부 특정 솔버만 지원하는 상태이다. 또한, 상용솔버와 비교해 표준 솔버는 일반적으로 수렴성이 좋지 않으며 격자의 품질에 민감하게 반응해 계산을 수행하는 것 자체가 어려운 경우도 적지 않다.</span> </p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 대상 유저&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈폼을 사용하려면 문제에 따라 기존의 솔버를 수정하거나 새로운 솔버 또는 라이브러리를 개발해야하는 경우가 적지않게 발생한다. 또한, 기본적으로 리눅스상에서 구동된다. 따라서, 유저는 리눅스를 다루는 것에 익숙하여야하며 C++를 이용한 프로그램을 개발할 수 있어야 하고 전산유체역학 이론과 해당 문제의 물리적 현상에 대해 알고 있어야 한다. 따라서, 주 대상 유저는 연구자나 학생, 수치계산에 충분한 시간을 들일 수 있는 엔지니어 등이 해당한다.</span></p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp;오픈 소스?&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈폼은 오픈 소스 소프트웨어이며 무료로 사용가능한 유체해석 소프트웨어로서 주목을 받고 있으나 "무료" 자체는 오픈 소스 소프트웨어의 성질에 해당하지 않는다. 오픈소스소프트웨어란 소스코드가 공개되어 있어 소스코드를 재배포 가능한 소프트웨어를 일컫는다. 이러한 성질에 의해 예를들어 소프트웨어를 유료로 하여도 구입한 사람이 무료로 소스코드를 재배포할 가능성이 크다. 그래서 결과적으로 무료로 제공하는 경우가 많다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">따라서, 유료의 오픈소스 소프트웨어도 존재할 수 있다. 개인 단위의 구매가 불가능한 가격(예를 들어 1억원 상당)을 붇이게 되면 재배포를 실직적으로 막을수 있다. 특히, 오픈폼과 같이 높은 전문성을 요구하는 소프트웨어의 경우 이것이 현실적으로 가능하다. 하지만, 소스코드의 내용에 대해 비밀유지계약을 체결하면 확실한 재배포를 막을 수 있다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈 소스 소프트웨어의 이용에 있어 아래와 같은 제약이 있다.</span></p>
<ul style="LIST-STYLE-TYPE: square">
<li>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">보증 불가능하다.</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">소스코드를 변수정한 소프트웨어를 제공할 경우, 제공처에 소스코드를 공개해야만 한다(GPL의 제한)</span></p></li></ul>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">2번째의 제약은 오픈폼을 포함해 리눅스를 시작으로하는 다수의 오픈소스 소프트웨어에 채용되어있는 라이센스인 GNU General Public License (GPL)의 제약이다.(정확히는 "GPL의 소프트웨어를 수정해 제공할 경우, 그 소프트웨어를 GPL에 제공해야한다". 이러한 제약을 "저주"라고 빈정거리는 사람도 있다) </span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">즉, 혼자서 사용하는데 제약은 없다. 하지만 무료이며 무보증이므로 사용에 있어 개인의 노력이 요구된다. 사용이 불편하며 지나치게 독특한 오픈소프트웨어도 적지않다(오픈폼도 예외되지 않는다). 이것은 "불편하면 상용소프트웨어를 쓰시오"라는 것이 아니라 "마음에 들지 않는 부분을 직접 개선해 프로젝트에 공헌해 주시오"의 의미이다. 사용자를 위한 매뉴얼이 존재하지 않는것도 많으며(이것 또한 오픈폼에도 해당) 웹상의 단편적인 정보나 소스코드로부터 필요한 정보를 찾아야 한다. 자신이 직접 문제를 해결하는것을 좋아하는 사람이 아니라면 오픈폼을 포함하는 오픈소스소프트웨어를 사용하는 것은 쉽지 않다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">사용에 있어 개인의 노력에 대해 비용(시간 등을 포함해)이 무료라고하는 금전적인 메리트를 훨씬 뛰어넘을 수 있다는 것을 고려해야한다. "값비싼" 상용 소프트웨어의 경우가 현실적인 선택지인 경우도 있으므로 오픈폼을 이용함에 있어 충분한 사전검토가 필요하다.</span></p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp;어떻게 사용할 것인가&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">먼저 오픈폼을 상용소프트웨어의 대체물로 생각한다면 오픈폼은 설정이 기본적으로 텍스트 베이스이며 솔버의 개발이나 수정을 필요로 하는 경우가 있으므로 일반적인 상용소프트웨어보다 훨씬 많은 수고를 들일 각오가 필요하다. 상용소프트웨어의 라이센스비와 오픈폼을 이용하며 늘어나는 인건비와 시간을 저울에 달고 비교해볼 필요가 있다. "무료"라는 것은 시간으로 돈을 사는것이다. 경우에 따라서는 돈으로 시간을 사는것이 올바른 선택일 수 있다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">상용 소프트웨어에서는 라이센스비용이 막대하게 증가하는 대규모병렬해석을 위해 오픈폼을 이용하는 경우가 있다. 현재 오픈폼을 이용하는 비용보다 대규모병렬해석용 상용라이센스의 경우가 압도적으로 고가이므로 대규모 병렬해석에 오픈폼을 사용하는 가치는 상당하다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">특정 제품의 설계 등 문제를 한정할 수 있는 경우 그것에 대한 솔버를 간이 인터페이스를 구성해 전용 설계툴로서 사용하는 경우가 있다. 물론 초기자본은 필요하나 한번 구성을 완료하면 유지비를 극소화할 수 있으므로 상용 소프트웨어를 이용하는 경우와 비교해 초기자금을 회수 할 수 있다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">현실적으로 상용소프트웨어를 구매할 수 없어 오픈폼을 이용하는 경우가 많으나 추천하지 않는다. 다른 선택지가 없는 경우라면 독학으로 어떻게든 하는 기개를 보여야 한다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">마지막으로 오픈폼은 오픈소스이며, 소스코드를 직접 볼수 있는 것이 큰 특징이다. 코드는 적절히 추상화되어 있어 나름대로 읽기쉽게 적혀 있으므로 전산유체역학을 학습하기 위한 좋은 교재로도 활용가능하다.</span></p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp;무엇부터 시작해야하는가&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4">(<span style="FONT-SIZE: 12pt">위의 글들을 읽고도 오픔폼을 사용할 마음이 있다면) 먼저 윈도우나 맥에서 가상머신(VirtualBox 또는 VMWare 등)에 사전에 오픈폼이 설치된 리눅스(DEXCS for OpenFOAM 등)을 셋업하는것이 편리하다. 또는 우분투를 설치하고 직접 오픈폼을 인스톨하는것도 어렵지 않다.</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈폼 환경이 준비되었다면 튜토리얼케이스를 실행해보는것이 좋다.</span></p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 오픈폼의 이용수단&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈폼을 사용하는 방법에는 아래와 같은 수단이 있다.</span></p>
<ul style="LIST-STYLE-TYPE: square">
<li>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈폼이 사전에 설치된 시스템을 도입</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">리눅스머신에 오픈폼을 설치</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">윈도우버전을 사용</span></p></li></ul>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 오픈폼이 사전에 설치된 시스템을 도입&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">리눅스나 오픈폼을 셋업하는 허들이 높게 느껴지는 사람들을 위해 오픈폼이 사전에 설치된 리눅스 환경이 제공되고 있다.</span></p>
<ul style="LIST-STYLE-TYPE: square">
<li>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">DEXCS for OpenFOAM</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">CAELinux</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">GeekoCFD</span></p></li></ul><br />
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 14px; FONT-FAMILY: sans-serif"><b><span style="FONT-SIZE: 12pt">- DEXCS for OpenFOAM&nbsp;</span></b></span><u><span style="FONT-SIZE: 12pt" 12px;?="" sans-serif;="" 22.695px;="" font-family:="" line-height:="" font-size:="">(</span><a style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px" href="http://dexcs.gifu-nct.ac.jp/"><span style="FONT-SIZE: 12pt">DEXCS</span></a><span style="FONT-SIZE: 12pt" sans-serif;="" 22.695px;?="" 9pt;="" font-family:="" line-height:="" font-size:="">)</span></u></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">원래 덴소의 사내교육용 시스템으로 개발된 것으로 ADVENTURE 를 사용하는 시스템이였으나, 오픈폼버전도 제공되고 있다.&nbsp;LiveDVD의 형태로 배포되며 하드디스크에 인스톨도 가능하다.&nbsp;LiveDVD의 형태로 배포되며 하드디스크에 인스톨도 가능하다.&nbsp;OpenFOAM 과 관련한 각종 툴도 동봉되어 있다.</span></p>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- CAELinux&nbsp;</span><u 22.695px;?="" 9pt;="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://www.caelinux.com/CMS/" ?=""><span style="FONT-SIZE: 12pt">CAELinux</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">OpenFOAM 뿐만 아니라 다양한 무료 CAE소프트웨어가 설치된 리눅스 환경.&nbsp;LiveDVD.</span></p>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- GeekoCFD</span><u style="FONT-SIZE: 9pt; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">(</span><a href="http://susestudio.com/a/2qtLK2/geekocfd"><span style="FONT-SIZE: 12pt">GeekoCFD</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">OpenFOAM 을 중심으로 하는 CFD관련 소프트웨어가 설치되어 있는 리눅스 환경.&nbsp;LiveDVD.</span></p>
<p style="LINE-HEIGHT: 2.4"><br /></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 리눅스 머신을 준비해 오픈폼을 설치&nbsp;</span></strong></td></tr></tbody></table></p>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">오픈폼은 리눅스용으로 개발되어있으며 리눅스머신에 설치하는것이 직관적이다. 리눅스를 도입하는 방법에는 아래와 같다.</span></p>
<ul style="LIST-STYLE-TYPE: square">
<li>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">리눅스&nbsp;전용 머신을 준비</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">윈도우/리눅스 듀얼부팅 환경을 구축</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">윈도우 위에 가상머신을 설치</span></p></li>
<li>
<p style="LINE-HEIGHT: 1"><span style="FONT-SIZE: 12pt">USB메모리 기동의 리눅스를 사용</span></p></li></ul>
<h2><span style="FONT-SIZE: 12pt">- Linux 전용머신을 준비</span></h2>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">가장 직관적인 방법. 강도높은 계산을 필요로 하는 사람에게 적합. 머신을 준비해 직접 리눅스를 설치하는 방법과 리눅스가 설치된 머신을 구입하는 방법이 있다.</span></p>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- Windows/Linux 듀얼부팅 환경을 구축</span></h3>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">Windows로도 Linux로도 사용가능한 머신을 준비. 하드디스크를 2개로 나누어 한쪽에는 윈도우 한쪽에는 리눅스를 설치한다. 이미 사용중인 윈도우 머신의 하드디스크에서 파티션을 구성해 리눅스를 설치하는것도 가능하다, 실패할경우 윈도우 환경이 파손될 우려가 있다.</span></p>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- Windows 위에 가상머신을 설치</span></h3><pfont-family: sans-serif;="" 22.695px;?="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">VirtualBox 또는 VMWare 등의 가상머신을 사용. 가장 안전한 방법에 해당하나 가상머신은 머신에 부담을 주게 되며 성능이 떨어진다. 최신의 가상화지원기능을 가지는 멀티CPU라면 적절히 사용가능할 수도 있다. SSD가 있으면 좋다. </span>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- USB 메모리 기동의 리눅스 사용</span></h3>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">USB 메모리에 리눅스를 넣어 사용. USB메모리 부팅이 가능한 머신을 준비할 필요가 있다. 파일시스템을 FAT32로 포맷(최대 4GB).</span></p>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- Distribution 배포판</span></h3>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">Linux 에는 Red Hat, openSUSE, Ubuntu 등의 다양한 "Distrubution"(배포 패키지)가 있으며 기본적으로는 모두 사용가능하다. 하지만&nbsp;OpenFOAM과 호환성이 좋지 않은 것도 존재한다. 최근에는&nbsp;Ubuntu 용의 OpenFOAM 바이너리 패키지가 배포되고 있으므로 우분투를 사용하는게 무난하다. 옛날 버전의 경우&nbsp;Ubuntu 이외에도&nbsp;openSUSE、Red Hat Enterprise Linux、Fedora용의 바이너리가 존재한다.</span></p>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- 문제점</span></h3><pfont-family: sans-serif;="" 22.695px;?="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">Linux 인스톨은 배포판과 머신의 호환성이 좋지 않은 경우도 있다. 또한, 오픈폼을과의 호환성이 문제가 되기도 한다. 문제해결을 위해 리눅스 시스템의 지식이나 프로그래밍 지식을 필요로 한다. 리눅스를 사용한다는 것 자체가 상당히 어려울 수 있다</span></pfont-family:></pfont-family:><span style="font-size: 12pt; line-height: 2.4;">.</span><p style="line-height: 2.4;"><span style="font-size: 12px; line-height: 2;">&nbsp;</span></p><div><pfont-family: sans-serif;="" 22.695px;?="" line-height:="" font-size:10pt;=""><p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""></p><table cellspacing="1" cellpadding="1" bgcolor="#ffffff" style="border-collapse: collapse;"><tbody><tr><td width="50%" style="border-bottom-color: rgb(103, 96, 96); border-bottom-width: 1px; border-bottom-style: solid; border-left-color: rgb(103, 96, 96); border-left-width: 12px; border-left-style: solid;"><strong style="font-size: 12px; color: rgb(103, 96, 96); line-height: 1.5;"><span style="font-size: 14pt;">&nbsp; Docker를 사용&nbsp;</span></strong></td></tr></tbody></table><p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="font-size: 16px; line-height: 38.4px;">Docker란, 컨테이너형 가상화 기술의 하나로, VirtualBox 와 같은 가상화에 비해 구동이 가볍다는 특징이 있다. OpenCFD사 버전의 OpenFOAM+ 가 Docker 컨테이너의 형태로 제공되고 있다.</span></p><ul style="list-style-type: square;"><li inherit;”=""><span style="font-size: 12pt;">OpenFOAM binary Installation (OpenCFD)</span></li><li inherit;”=""><span style="font-size: 12pt;">OpenFOAM Installation on Windows (OpenCFD)</span></li></ul></pfont-family:></div><div><span style="font-size: 16px; line-height: 38.4px;">Linux/Windows/Mac OS X 어디에서는 작동한다. 컨테이너의 내용물은 Linux이므로, 이론적으로는 기능을 모두 사용가능하지만 윈도우 버전은 포스트를 컨테이너에서 기동하는것이 불편하다. 컨테이너의 기동시간을 제외하면 솔버의 실행속도는 윈도우용으로 컴파일 된 버전의 속도가 조금 빠른 것 같다.</span></div><div><span style="font-size: 16px; line-height: 38.4px;">만약 그럴 의도가 있다면, Docker를 이용해 자신만의 OpenFOAM 환경을 구축하는것이 가능하다. &nbsp;SSH/X11 을 이용하면 윈도우에서 도 컨테이너에서 포스트를 사용할 수 있다. 하지만 환경구축이 쉽지많은 않다.</span></div><div><span style="FONT-SIZE: 16px; LINE-HEIGHT: 24px"><br /></span><pfont-family: sans-serif;="" 22.695px;?="" line-height:="" font-size:10pt;=""><pfont-family: sans-serif;="" 22.695px;?="" line-height:="" font-size:10pt;="">
<p style="LINE-HEIGHT: 2">&nbsp;</p>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 윈도우 버전을 사용&nbsp;</span></strong></td></tr></tbody></table></p>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">본래 리눅스용으로 개발된 오픈폼이지만 윈도우버전도 존재한다.</span></p>
<ul style="LIST-STYLE-TYPE: square">
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">O</span><span style="font-size: 16px; line-height: 24px;">penFOAM for Windows (Creative Fields)</span></li>
<li inherit;”=""><span style="font-size: 12pt;">simFlow engine (OpenFOAM for Windows)</span></li>
<li style="“list-style-type: " inherit;”=""><span style="font-size: 16px; line-height: 24px;">OpenFOAM for Windows (CFD support)</span></li>
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">Caelus</span></li>
<div><br /></div></ul>
<p><span style="FONT-SIZE: 12pt">과거 버전들</span></p>
<div>
<ul style="LIST-STYLE-TYPE: square">
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">OpenFOAM extensions</span></li>
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">OpenFOAM for MS windows binary release</span></li>
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">OpenFOAM 1.6 binary for win32</span></li>
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">OpenFOAM 2.1.x for Win64</span></li>
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">OpenFlow</span></li>
<li style="“list-style-type: " inherit;”=""><span style="FONT-SIZE: 12pt">blueCFD</span></li></ul>
<h3></h3>
<h3 style="“color: " sans-serif;="" 22.695px;”="" rgb(102,="" 153,="" 0);="" font-family:="" line-height:=""><br /></h3>
<h3 style="“color: " sans-serif;="" 22.695px;”="" rgb(102,="" 153,="" 0);="" font-family:="" line-height:=""><span style="FONT-SIZE: 12pt">- OpenFOAM for Windows (Creative Fields)</span><span style="FONT-SIZE: 12pt">&nbsp;</span><u><span style="FONT-SIZE: 12pt" 10pt;="" 22.695px;”="" line-height:="" font-size:="">(</span><a style="“font-size: " href="http://onedayof.tistory.com/admin/entry/post/“http://www.c-fields.com/downloads”" 22.695px;="" 10pt;="" ”="" line-height:=""><span style="FONT-SIZE: 12pt">Creative Fields</span></a><span style="FONT-SIZE: 12pt" 10pt;="" 22.695px;”="" line-height:="" font-size:="">)</span></u></h3>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">Version 2.3.0, 3.1 (extend) 의 Windows 바이너리 제공.</span></p>
<h3 style="“color: " sans-serif;="" 22.695px;”="" rgb(102,="" 153,="" 0);="" font-family:="" line-height:=""><span style="FONT-SIZE: 12pt">- simFlow engine (OpenFOAM for Windows)</span><span style="FONT-SIZE: 12pt">&nbsp;</span><u 10pt;="" 22.695px;”="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“https://sim-flow.com/download/openfoam-windows/“"><span style="FONT-SIZE: 12pt">simFlow</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">Version 2.3.0, 2.3.1 의 Windows&nbsp;</span><span style="FONT-SIZE: 12pt" 22.695px;”="">바이너리 제공. 패치도 제공되고 있다.</span></p>
<h3 style="“color: " sans-serif;="" 22.695px;”="" rgb(102,="" 153,="" 0);="" font-family:="" line-height:=""><span style="FONT-SIZE: 12pt">- OpenFOAM for Windows (CFD support)</span><span style="FONT-SIZE: 12pt">&nbsp;</span><u 10pt;="" 22.695px;”="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“http://www.cfdsupport.com/openfoam-for-windows.html”"><span style="FONT-SIZE: 12pt">CFD support</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">Version 2.3.x 의&nbsp;Windows&nbsp;</span><span style="FONT-SIZE: 12pt" 22.695px;="" 12px;”="" font-size:="">바이너리 제공</span><span style="font-size: 12pt; line-height: 1.5;">.</span></p><h3 sans-serif;="" 22.695px;”="" rgb(102,="" 153,="" 0);="" font-family:="" line-height:=""><span style="font-size: 12pt;">- Caelus (<a href="https://www.caelus-cml.com/" target="_blank" class="tx-link">Caelus (Applied CCM)</a>)</span></h3><p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="font-size: 12pt;">OpenFOAM의 fork 인듯하다. Windows 바이너리 제공</span></p>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span 22.695px;="" 12px;”="" font-size:="" style="font-size: 12pt;"><br /></span></p>
<h3 style="“color: " sans-serif;="" 22.695px;”="" rgb(102,="" 153,="" 0);="" font-family:="" line-height:=""><span style="FONT-SIZE: 12pt">과거 버전들</span></h3>
<h4 style="“color: " sans-serif;="" 22.695px;”="" 153,="" 0);="" rgb(204,="" 7.69886px;="" font-family:="" line-height:="" font-size:10pt;="" padding-left:=""><span style="FONT-SIZE: 12pt">- OpenFOAM extensions&nbsp;</span><u 10pt;="" 22.695px;”="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“http://sourceforge.net/projects/openfoam-extend”"><span style="FONT-SIZE: 12pt">OpenFOAM extensions</span></a><span style="FONT-SIZE: 12pt">)</span></u></h4>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">&nbsp; &nbsp; 1.4 의&nbsp;Cygwin 판을 제공.</span></p>
<h4 style="“color: " sans-serif;="" 22.695px;”="" 153,="" 0);="" rgb(204,="" 7.69886px;="" font-family:="" line-height:="" font-size:10pt;="" padding-left:=""><span style="FONT-SIZE: 12pt">- OpenFOAM for MS windows binary release&nbsp;</span><u 10pt;="" 22.695px;”="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“http://sourceforge.net/projects/openfoam-mswin/“"><span style="FONT-SIZE: 12pt">OpenFOAM for MS windows binary release</span></a><span style="FONT-SIZE: 12pt">)</span></u></h4>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">&nbsp; &nbsp; Windows 네이티브인 OpenFOAM. 1.5 베이스. 몇몇 솔버가 이식되어 있다.</span></p>
<h4 style="“color: " sans-serif;="" 22.695px;”="" 153,="" 0);="" rgb(204,="" 7.69886px;="" font-family:="" line-height:="" font-size:10pt;="" padding-left:=""><span style="FONT-SIZE: 12pt">- OpenFOAM 1.6 binary for win32&nbsp;</span><u 10pt;="" 22.695px;”="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“http://sourceforge.net/projects/openfoam16wi32/“"><span style="FONT-SIZE: 12pt">OpenFOAM 1.6 binary for win32</span></a><span style="FONT-SIZE: 12pt">)</span></u></h4>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">&nbsp; &nbsp; Windows&nbsp;</span><span style="FONT-SIZE: 12pt" 22.695px;”="">네이티브인&nbsp;</span><span style="FONT-SIZE: 12pt">&nbsp;OpenFOAM&nbsp;1.6 베이스. 병렬계산 불가능.</span></p>
<h4 style="“color: " sans-serif;="" 22.695px;”="" 153,="" 0);="" rgb(204,="" 7.69886px;="" font-family:="" line-height:="" font-size:10pt;="" padding-left:=""><span style="FONT-SIZE: 12pt">- OpenFOAM 1.7.0 for Win32&nbsp;</span><u 10pt;="" 22.695px;”="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“http://sourceforge.net/projects/openfoam-170/?source=directory”"><span style="FONT-SIZE: 12pt">OpenFOAM 1.7.0 for Win32</span></a><span style="FONT-SIZE: 12pt">)</span></u></h4>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">&nbsp; &nbsp; Windows&nbsp;</span><span style="FONT-SIZE: 12pt" 22.695px;”="">네이티브인&nbsp;</span><span style="FONT-SIZE: 12pt">OpenFOAM&nbsp;1.7. 병렬계산이 가능하다고 한다.</span></p>
<h4 style="“color: " sans-serif;="" 22.695px;”="" 153,="" 0);="" rgb(204,="" 7.69886px;="" font-family:="" line-height:="" font-size:10pt;="" padding-left:=""><span style="FONT-SIZE: 12pt">- OpenFOAM 2.1.x for Win64&nbsp;</span><u><span style="FONT-SIZE: 12pt" 10pt;="" 22.695px;”="" line-height:="" font-size:="">(</span><a style="“font-size: " href="http://onedayof.tistory.com/admin/entry/post/“http://sourceforge.net/projects/openfoam21win64/“" 22.695px;="" 10pt;="" ”="" line-height:=""><span style="FONT-SIZE: 12pt">OpenFOAM 2.1.x for Win64</span></a><span style="FONT-SIZE: 12pt" 10pt;="" 22.695px;”="" line-height:="" font-size:="">)</span></u></h4>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">&nbsp; &nbsp; Windows&nbsp;</span><span style="FONT-SIZE: 12pt" 22.695px;”="">네이티브인&nbsp;</span><span style="FONT-SIZE: 12pt">OpenFOAM 2.1.x. Open MPI 를 이용한 병렬계산 가능.</span></p>
<h4 style="“color: " sans-serif;="" 22.695px;”="" 153,="" 0);="" rgb(204,="" 7.69886px;="" font-family:="" line-height:="" font-size:10pt;="" padding-left:=""><span style="FONT-SIZE: 12pt">- OpenFlow&nbsp;</span><u><span style="FONT-SIZE: 12pt" 10pt;="" 22.695px;”="" line-height:="" font-size:="">(</span><a style="“font-size: " href="http://onedayof.tistory.com/admin/entry/post/“http://www.symscape.com/product/openflow”" 22.695px;="" 10pt;="" ”="" line-height:=""><span style="FONT-SIZE: 12pt">Symscape</span></a><span style="FONT-SIZE: 12pt" 10pt;="" 22.695px;”="" line-height:="" font-size:="">)</span></u></h4>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">&nbsp; &nbsp; Windows 용으로 빌드한&nbsp;OpenFOAM (유료). 빌드순서와 패치 공개.&nbsp;</span><u><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“http://www.symscape.com/openfoam-2-2-x-on-windows”"><span style="FONT-SIZE: 12pt">OpenFOAM 2.2.x on Windows</span></a><span style="FONT-SIZE: 12pt">)</span></u><span style="FONT-SIZE: 12pt">.</span></p>
<h4 style="“color: " sans-serif;="" 22.695px;”="" 153,="" 0);="" rgb(204,="" 7.69886px;="" font-family:="" line-height:="" font-size:10pt;="" padding-left:=""><span style="FONT-SIZE: 12pt">&nbsp;- blueCFD&nbsp;</span><u 10pt;="" 22.695px;”="" line-height:="" font-size:=""><span style="FONT-SIZE: 12pt">(</span><a href="http://onedayof.tistory.com/admin/entry/post/“http://joomla.bluecape.com.pt/index.php?option=com_content&amp;task=view&amp;id=18&amp;Itemid=30&amp;lang=en”"><span style="FONT-SIZE: 12pt">blueCAPE</span></a><span style="FONT-SIZE: 12pt">)</span></u></h4>
<p sans-serif;="" 22.695px;”="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">&nbsp; &nbsp; Windows&nbsp;</span><span style="FONT-SIZE: 12pt" 22.695px;”="">용으로 빌드한</span><span style="FONT-SIZE: 12pt">&nbsp;OpenFOAM + α&nbsp;</span><span style="FONT-SIZE: 12pt" 22.695px;”="">(유료). 싱글코어용은 무료<span style="line-height: 38.4px;">.</span></span></p>
<p style="LINE-HEIGHT: 2"><br /></p></div>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 관련 프로젝트&nbsp;</span></strong></td></tr></tbody></table></p>
<ul style="LIST-STYLE-TYPE: square">
<li><span style="FONT-SIZE: 12pt">OpenFOAM extensions</span></li>
<li><span style="FONT-SIZE: 12pt">PyFoam</span></li>
<li><span style="FONT-SIZE: 12pt">swak4Foam</span></li>
<li><span style="FONT-SIZE: 12pt">Discretizer</span></li>
<li><span style="FONT-SIZE: 12pt">Helyx-OS</span></li>
<li><span style="FONT-SIZE: 12pt">cfMesh</span></li></ul>
<h3 style="FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- OpenFOAM extensions&nbsp;</span><u style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">(</span><a href="http://sourceforge.net/projects/openfoam-extend"><span style="FONT-SIZE: 12pt">OpenFOAM extensions</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">OpenFOAM 확장판.&nbsp;Git 또는 SVN 를 이용해 제공.</span></p>
<ul style="LIST-STYLE-TYPE: square; LINE-HEIGHT: 22px">
<li><span style="FONT-SIZE: 12pt">Git: OpenFOAM-1.6-ext,foam-extend-3.0,foam-extend-3.1</span></li>
<li><span style="FONT-SIZE: 12pt">SVN: OpenFOAM-1.4-dev,OpenFOAM-1.4.1-dev,OpenFOAM-1.5-dev,OpenFOAM-1.6-ext(trunk/Core 중)</span></li></ul>
<p style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">Files 에는 바이너리 패키지도 있다.</span></p>
<h3 style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- PyFoam&nbsp;</span><u style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">(</span><a href="http://openfoamwiki.net/index.php/Contrib_PyFoam"><span style="FONT-SIZE: 12pt">PyFoam</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">Python 으로 OpenFOAM 의 데이터 조작 가능. 계산중의 Residual변화를 gnuplot에 표시하는 커맨드 등이 있다.</span></p>
<h3 style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- swak4Foam&nbsp;</span><u style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">(</span><a href="http://openfoamwiki.net/index.php/Contrib/swak4Foam"><span style="FONT-SIZE: 12pt">swak4Foam</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">복잡한 경계조건을 설정할 수 있는 툴이 포함되어 있다.</span></p>
<h3 style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- Discretizer&nbsp;</span><u style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">(</span><a href="http://www.discretizer.org/"><span style="FONT-SIZE: 12pt">Discretizer</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">OpenFOAM 용 GUI 툴.</span></p>
<h3 style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- Helyx-OS&nbsp;</span><u style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">(</span><a href="http://sourceforge.net/projects/helyx-os/"><span style="FONT-SIZE: 12pt">Helyx-OS</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">OpenFOAM&nbsp;</span><span style="FONT-SIZE: 12pt; LINE-HEIGHT: 22px">용 GUI 툴.</span></p>
<h3 style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">- cfMesh&nbsp;</span><u style="LINE-HEIGHT: 22px"><span style="FONT-SIZE: 12pt">(</span><a href="http://sourceforge.net/projects/cfmesh/" ?=""><span style="FONT-SIZE: 12pt">cfMesh</span></a><span style="FONT-SIZE: 12pt">)</span></u></h3>
<p sans-serif;="" 22.695px;?="" font-family:="" line-height:="" font-size:10pt;=""><span style="FONT-SIZE: 12pt">OpenFOAM 용 자동 격자생성기</span><span style="font-size: 12pt; line-height: 1.5;">.</span></p><div><p style="line-height: 2;"><br /></p></div><table cellspacing="1" cellpadding="1" bgcolor="#ffffff" style="border-collapse: collapse;"><tbody><tr><td width="50%" style="border-bottom-color: rgb(103, 96, 96); border-bottom-width: 1px; border-bottom-style: solid; border-left-color: rgb(103, 96, 96); border-left-width: 12px; border-left-style: solid;"><strong style="font-size: 12px; color: rgb(103, 96, 96); line-height: 1.5;"><span style="font-size: 14pt;">&nbsp; 표준솔버 이외의 솔버&nbsp;</span></strong></td></tr></tbody></table><br /><ul style="list-style-type: square;"><li><span style="font-size: 12pt;">CFDEM</span></li><li><span style="font-size: 12pt;">OpenQBMM</span></li><li><span style="font-size: 12pt;">S-CLSVOF법 솔버</span></li><li><span style="font-size: 12pt;">EDC 솔버</span></li><li><span style="font-size: 12pt;">flameletFoam</span></li></ul><h3 style="font-family: sans-serif; line-height: 22px;"><span style="font-size: 12pt;">- CFDEM (<a href="http://www.cfdem.com/" target="_blank" class="tx-link">CFDEM project</a>)</span></h3><p style="line-height: 22px;"><span style="font-size: 12pt;">OpenFOAM 과 DEM 솔버 LIGGHTS 로 CFD-DEM 연성을 수행</span></p><h3 style="line-height: 22px;"><span style="font-size: 12pt;">- OpenQBMM (<a href="https://www.openqbmm.org/" target="_blank" class="tx-link">OpenQBMM</a>)</span></h3><p style="line-height: 22px;"><span style="font-size: 12pt;">OpenFOAM에 의한 Quadrature-Based Moments Methods (QBMM)을 이용한 다분산계혼합류 솔버</span></p><h3 style="line-height: 22px;"><span style="font-size: 12pt;">- S-CLSVOF법 솔버</span></h3><ul style="list-style-type: square; line-height: 22px;"><li><span style="font-size: 12pt;"><a href="http://www.slideshare.net/takuyayamamoto1800/openfoam-35433342" target="_blank" class="tx-link">OpenFOAM의 혼합류용 개선 솔버(S-CLSVOF법)의 설정, 사용방법 (SlideShare)</a></span></li><li><span style="font-size: 12pt;"><a href="https://bitbucket.org/nunuma/public/src" target="_blank" class="tx-link">코드 (Bitbucket)</a></span></li></ul><p style="line-height: 22px;"><span style="font-size: 12pt;">S-CLSVOF법을 구현. interFoam의 설명도 참고하면 좋다</span></p><h3 style="line-height: 22px;"><span style="font-size: 12pt;">-&nbsp;EDC 솔버</span></h3><ul style="list-style-type: square; line-height: 22px;"><li><span style="font-size: 12pt;"><a href="http://openfoamwiki.net/index.php/Sig_CombustionReactingFlows_/_Tutorials" target="_blank" class="tx-link">Sig CombustionReactingFlows / Tutorials (OpenFOAM Wiki)</a></span></li><li><span style="font-size: 12pt;"><a href="https://sourceforge.net/p/ofca/code/ci/master/tree/" target="_blank" class="tx-link">OpenFOAM-Combustion-Addon (SourceForge)</a></span></li></ul><p style="line-height: 22px;"><span style="font-size: 12pt;">EDC 솔버. 조금은 오래됬지만 참고할만 하다.</span></p>
<p style="line-height: 22px;"><span style="font-size: 12pt;">또, simFlow-engine의 레포지토리에 왠일인지 EDC 솔버가 포함되어있는 시기가 있다 (<a href="https://sourceforge.net/p/simflowengine22/code/ci/dc41944be1e05337ec70f999109c723aa58e432e/tree/" target="_blank" class="tx-link">simFlows-engine-2.2</a>).</span></p><h3 style="line-height: 22px;"><span style="font-size: 12pt;">- flameletFoam</span></h3><p style="line-height: 22px;"><span style="font-size: 12pt;"><a href="http://openfoamwiki.net/index.php/Extend-bazaar/solvers/combustion/flameletFoam" target="_blank" class="tx-link">Extend-bazarr/solvers/combustion/flameletFoam (OpenFOAM Wiki)</a></span></p>
<p style="line-height: 22px;"><span style="font-size: 12pt;">flamelet 솔버</span></p>
<p style="LINE-HEIGHT: 2"><br /></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 소스코드를 읽기위한 툴&nbsp;</span></strong></td></tr></tbody></table></p>
<div></div>
<p style="LINE-HEIGHT: 0.2"></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">솔버를 사용만 하려면 필요가 없으나 소스코드를 이해하고싶다면 그 전용 툴을 사용하면 좋다. 클래스 정의로의 이동이 편리하다.</span></p>
<ul style="LIST-STYLE-TYPE: square">
<li><a href="http://www.eclipse.org/" ?=""><u><span style="FONT-SIZE: 12pt">Eclipse</span></u></a></li>
<li><a href="http://ja.netbeans.org/" ?=""><u><span style="FONT-SIZE: 12pt">NetBeans</span></u></a></li></ul>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">프로젝드를 작성해 프로젝트의 디렉토리를 오픈폼 디렉토리로 설정하면 된다(파일이 많으므로 프로젝트 작성에 시간이 걸린다).</span></p>
<p style="LINE-HEIGHT: 2.4"><span style="FONT-SIZE: 12pt">코드를 직접 읽지 않고, </span><u><a class="tx-link" href="http://www.openfoam.org/docs/cpp/" target="_blank"><span style="FONT-SIZE: 12pt">Doxygen의 문서</span></a></u><span style="FONT-SIZE: 12pt">를 참고하는 방법도 있다. 개인적으로는 </span><u><a class="tx-link" href="https://www.gnu.org/software/global/" target="_blank"><span style="FONT-SIZE: 12pt">GNU GLOBAL</span></a></u><span style="FONT-SIZE: 12pt">을 좋아한다</span><span style="font-size: 12pt; line-height: 2.4;">.</span></p>
<p style="line-height: 2.4;"><br /></p>
<p style="line-height: 0.2;"></p>
<p style="line-height: 2.4;"></p><table cellspacing="1" cellpadding="1" bgcolor="#ffffff" style="border-collapse: collapse;"><tbody><tr><td width="50%" style="border-bottom-color: rgb(103, 96, 96); border-bottom-width: 1px; border-bottom-style: solid; border-left-color: rgb(103, 96, 96); border-left-width: 12px; border-left-style: solid;"><p><strong style="font-size: 12px; color: rgb(103, 96, 96); line-height: 1.5;"><span style="font-size: 14pt;">&nbsp;오픈폼 버전에 대해&nbsp;</span></strong></p></td></tr></tbody></table><p style="line-height: 0.2;"></p>
<p style="line-height: 2.4;"><span style="font-size: 12pt;">오픈폼의 버전에 대해서는, 특별이 문제가 되지 않는다면 최신버전을 사용하는것이 좋으나 유저가 작성해 공개한 솔버나 라이브러리는 예전 버전에서 작성된게 많으므로 그런 것들을 사용하려면 대응하는 버전 (버전 2.x 계통인 경우가 많다)을 사용해야 한다.&nbsp;최신버전을 위한 환경을 준비할 수 없거나, 이미 옛버전에서 구축된 솔버나 라이브러라가 있어서 어쩔 수 없이 옛 버전을 사용하는 경우가 빈번한데 크게 문제되지는 않는다(여유가 된다면 최신의 버그정보를 찾아봐두면 좋다).</span></p>
<p style="line-height: 2.4;"><span style="font-size: 12pt;">OpenFOAM의 버전은, 예를들어 2.4.0 이라는것과 2.4.x 이라는 것이 있다. 2.4.0 이 공식배포판이며 2.4.x 는 버그수정버전에 해당한다(<a href="http://www.cfd-online.com/Forums/openfoam/150437-whats-difference-openfoam-dev-openfoam-2-x-x.html#post537720" target="_blank" class="tx-link">Whats the difference of OpenFOAM-dev and OpenFOAM-2.x.x?</a>). 특별히 상관없다면 공식공개버전을 사용하면 된다. 또한 별도의 OpenFOAM-dev 라는것도 있으며, 이것은 개발자버전에 해당한다. 2.4.x 나 OpenFOAM-dev 는&nbsp;<a href="https://github.com/OpenFOAM" target="_blank" class="tx-link">GitHub 레포지토리</a>에 있다.</span></p>
<p style="line-height: 2.4;"><span style="font-size: 12pt;">OpenFOAM Foundation 버전의 openFOAM과 OpenCFD (ESI) 버전의 OpenFOAM+ 의 차이는, OpenFOAM v3.0+ ?? 에 있듯이, RHEL과 Fedora의 차이와 같은 개념 정도이다. 아마도 자기 마음대로 하고싶은 Weller씨와 커뮤니티의 요구사항을 받아들이고 싶은 ESI의 견해차이가 낳은 구분인 것 같다. 어느쪽이 어떻게 될지는 좀 더 지켜봐야 할 것 같다.</span></p>
<p style="LINE-HEIGHT: 2"><br /></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 관련문헌&nbsp;</span></strong></td></tr></tbody></table></p>
<ul style="LIST-STYLE-TYPE: square; FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px">
<li><a href="http://powerlab.fsb.hr/ped/kturbo/OpenFOAM/docs/HrvojeJasakPhD.pdf" ?=""><u><span style="FONT-SIZE: 12pt">H. Jasak, Error analysis and estimation in the Finite Volume method with applications to fluid flows, Thesis, Imperial College, London, 1996</span></u></a></li>
<li><a href="http://powerlab.fsb.hr/ped/kturbo/openfoam/docs/foam.pdf" ?=""><u><span style="FONT-SIZE: 12pt">H.G. Weller, G. Tabor, H. Jasak, C. Fureby, A tensorial approach to computational continuum mechanics using object-oriented techniques, Computers in physics, 1998</span></u></a></li>
<li><a href="http://powerlab.fsb.hr/ped/kturbo/Openfoam/papers/LinearStressPaper.pdf"><u><span style="FONT-SIZE: 12pt">H. Jasak, H.G. Weller, Application of the finite volume method and unstructured meshes to linear elasticity, International journal for numerical methods in engineering, 2000</span></u></a></li></ul>
<p style="LINE-HEIGHT: 2"><span style="font-size: 16px; line-height: 38.4px;">첫번째 논문이 OpenFOAM 유저로써 가장 중요한 논문이다</span><span style="font-size: 12pt; line-height: 2.4;">.</span></p>
<p style="line-height: 2;"><br /></p><table cellspacing="1" cellpadding="1" bgcolor="#ffffff" style="border-collapse: collapse;"><tbody><tr><td width="50%" style="border-bottom-color: rgb(103, 96, 96); border-bottom-width: 1px; border-bottom-style: solid; border-left-color: rgb(103, 96, 96); border-left-width: 12px; border-left-style: solid;"><strong style="font-size: 12px; color: rgb(103, 96, 96); line-height: 1.5;"><span style="font-size: 14pt;">&nbsp; 참고도서&nbsp;</span></strong></td></tr></tbody></table><br /><ul style="list-style-type: square; font-family: sans-serif; line-height: 22px;"><li><span style="font-size: 12pt;">Suhas V. Patankar, Numerical Heat Transfrer and Fluid Flow, 1980</span></li><li><span style="font-size: 12pt;">Joel H. Ferziger and M. Peric, Computational Methods for Fluid Dynamics, Springer, 2002</span></li><li><span style="font-size: 12pt;">H. K. Versteeg and W. Malalasekera,n Introduction to Computational Fluid Dynamics, Pretense Hall, 2007</span></li></ul><p style="line-height: 2;"><span style="font-size: 16px; line-height: 38.4px;">첫번째 파탄카의 책은 수치유체역학을 공부하는데 기본중 기본이다. 하지만 표현이 오픈폼과 맞지 않다. 퍼지거의 책은 표현이 오픈폼에 가까워 오픈폼을 이해하는데 참고하기 좋다. Versteeg의 책은 난류모델이나 이산화스킴에 대해 이해하기 쉽게 설명되어 있다.</span></p>
<p style="LINE-HEIGHT: 2"><br /></p>
<p>
<table style="BORDER-COLLAPSE: collapse" cellspacing="1" cellpadding="1" bgcolor="#ffffff">
<tbody>
<tr>
<td style="BORDER-BOTTOM: #676060 1px solid; BORDER-LEFT: #676060 12px solid" width="50%"><strong style="FONT-SIZE: 12px; COLOR: rgb(103,96,96); LINE-HEIGHT: 1.5"><span style="FONT-SIZE: 14pt">&nbsp; 관련링크&nbsp;</span></strong></td></tr></tbody></table></p>
<ul style="LIST-STYLE-TYPE: square; FONT-FAMILY: sans-serif; LINE-HEIGHT: 22px">
<li><a href="http://www.openfoam.org/" ?=""><u><span style="FONT-SIZE: 12pt">OpenFOAM Foundation</span></u></a></li>
<li><a href="http://www.openfoam.com/" ?=""><u><span style="FONT-SIZE: 12pt">OpenCFD</span></u></a></li>
<li><a href="http://sourceforge.net/projects/foam/"><u><span style="FONT-SIZE: 12pt">OpenFOAM - The Open Source CFD Toolbox</span></u></a><span style="FONT-SIZE: 12pt">&nbsp;옛 버전은 여기서 다운로드 가능.</span></li>
<li><a href="https://github.com/OpenFOAM" ?=""><u><span style="FONT-SIZE: 12pt">Official OpenFOAM Repository (GitHub)</span></u></a></li>
<li><a href="http://openfoamwiki.net/index.php/Main_Page"><u><span style="FONT-SIZE: 12pt">OpenFOAM Wiki</span></u></a></li>
<li><a href="http://www.cfd-online.com/Forums/openfoam/"><u><span style="FONT-SIZE: 12pt">CFD Online OpenFOAM Forum</span></u></a></li>
<li><u><span style="FONT-SIZE: 12pt"><a href="http://powerlab.fsb.hr/ped/kturbo/OpenFOAM/">http://powerlab.fsb.hr/ped/kturbo/OpenFOAM/</a></span></u><span style="font-size: 16px;">&nbsp; OpenFOAM 관련 논문이 있다.</span></li></ul></pfont-family:></pfont-family:></div></div></div><a href="http://powerlab.fsb.hr/ped/kturbo/OpenFOAM/">
<p><br /></p></a></div><a href="http://powerlab.fsb.hr/ped/kturbo/OpenFOAM/">
<p><br /></p></a><p><br /></p>
