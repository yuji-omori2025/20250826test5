section>

<h2>list-normal2</h2>

<ul class="disc">
<li>背景画像はcssで設定します。</li>
<li>デフォルトだとテキストブロックは左側に配置されます。逆にしたい場合（下の「鳥シリーズ」）は<br>
text-parts<br>
を<br>
text-parts reverse-parts<br>
にすればOKです。「reverse-parts」がつくことで配置が逆になります。お好みで使い分けて下さい。</li>
<li>外側の余白をなくしたい場合は<a href="https://template-party.com/parts/manual.html">こちらのマニュアル</a>をご覧下さい。</li>
</ul>

<div class="parts-list-normal2 image1-parts">

<div class="text-parts">

<h3><span class="large-parts">花</span>シリーズ<span>Series Title</span></h3>
<p>ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。</p>
<p class="btn-parts"><a href="#">View More</a></p>

</div>

</div>

<div class="parts-list-normal2 image2-parts">

<div class="text-parts reverse-parts">

<h3><span class="large-parts">鳥</span>シリーズ<span>Series Title</span></h3>
<p>ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。</p>
<p class="btn-parts"><a href="#">View More</a></p>

</div>

</div>

<div class="parts-list-normal2 image3-parts">

<div class="text-parts">

<h3><span class="large-parts">風</span>シリーズ<span>Series Title</span></h3>
<p>ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。ここに説明文を入れます。サンプルテキスト。</p>
<p class="btn-parts"><a href="#">View More</a></p>

</div>

</div>

</section>
/*parts-list-normal2
---------------------------------------------------------------------------*/
/*１枚目の写真*/
.parts-list-normal2.image1-parts {
	background: url("../images/1.jpg") no-repeat center center / cover;
}

/*２枚目の写真*/
.parts-list-normal2.image2-parts {
	background: url("../images/2.jpg") no-repeat center center / cover;
}

/*３枚目の写真*/
.parts-list-normal2.image3-parts {
	background: url("../images/3.jpg") no-repeat center center / cover;
}

/*ボックス１個あたり*/
.parts-list-normal2 {
	padding: 5vw;	/*ボックス内の余白。画面幅100%＝100vwです。*/
	position: relative;
	overflow-x: hidden;
	margin-bottom: 1vw;	/*下に空けるスペース。ボックス同士の隙間です。*/
}

/*マウスオン用のアニメーション*/
.parts-list-normal2::before {
	content: "";position: absolute;top: 0;left: 0;width: 100%;height: 100%;
	background: rgba(0,0,0,0.6);		/*写真に重ねておく半透明の黒い色。0,0,0は黒のことで0.6は色が60%出た状態。*/
	transition: transform 0.5s 0.1s;	/*アニメーションの速度（0.5秒）と待機時間（0.1秒）。*/
}
.parts-list-normal2:hover::before {
	transform: translateX(100%);	/*マウスオンで半透明の黒を枠外へ出す。-100%にすると逆に移動します。*/
}

/*テキストブロック*/
.parts-list-normal2 .text-parts {
	position: relative;z-index: 1;
	width: 80%;		/*幅*/
	height: 100%;
	color: #fff;	/*文字色*/
	text-shadow: 1px 1px 2px rgba(0,0,0,0.3);	/*テキストの影。右へ、下へ、ぼかし幅、0,0,0は黒のことで0.3は色が30%出た状態。*/
}

	/*画面幅600px以上の追加指定*/
	@media screen and (min-width:600px) {

	/*テキストブロック*/
	.parts-list-normal2 .text-parts {
		width: 40%;		/*幅*/
	}

	}/*追加指定ここまで*/


/*テキストの配置場所を入れ替えたい場合のスタイル。*/
.parts-list-normal2 .text-parts.reverse-parts {
	margin-left: auto;
}

/*parts-list-normal2内のh3見出し*/
.parts-list-normal2 h3 {
	margin: 0;padding: 0;
	font-weight: normal;	/*h要素のデフォルトの太字を標準に*/
	position: relative;
	font-size: 2rem;		/*文字サイズを200%*/
	letter-spacing: 0.1rem;	/*文字間隔を少しだけ広く*/
	line-height: 1.2;		/*行間を狭くする*/
}

/*parts-list-normal2内のh3見出し内の１文字目の大きな文字*/
.parts-list-normal2 h3 .large-parts {
	font-size: 7rem;	/*文字サイズを7倍*/
}

/*見出しの右上にある英語の小さな文字*/
.parts-list-normal2 h3 span:not(.large-parts) {
	font-size: 1rem;	/*文字サイズを標準に戻す*/
	opacity: 0.5;		/*透明度50%*/
	position: absolute;
	right: 0px;	/*右からの配置場所*/
	top: 0px;	/*上からの配置場所*/
}


/*ボタン
---------------------------------------------------------------------------*/
.parts-list-normal2 .btn-parts a {
	display: block;text-decoration: none;
	padding: 0.8rem 2rem;	/*上下、左右へのボタン内の余白*/
	margin-top: 2rem;		/*ボタンの上に2文字分のスペースを空ける*/
	text-align: center;		/*テキストをセンタリング*/
	letter-spacing: 0.1em;	/*文字間隔を少しだけ広く*/
	box-shadow: 0px 10px 30px rgba(0,0,0,0.1);	/*ボタンの影。右へ、下へ、ぼかし幅、0,0,0は黒のことで0.1は色が10%出た状態*/
	color: #fff;	/*文字色*/
	border: 1px solid #fff;	/*枠線の幅、線種、色*/
}

/*マウスオン時*/
.parts-list-normal2 .btn-parts a:hover {
	letter-spacing: 0.2rem;	/*文字間隔を少し広げる*/
	box-shadow: none;		/*ボタンの影を消す*/
}
.parts-list-normal2:hover .btn-parts a {
	background: rgba(0,0,0,0.8);	/*背景色。0,0,0は黒のことで0.8は色が80%出た状態。*/
}
