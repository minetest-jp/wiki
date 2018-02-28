---
title: Mod解説 - Pipeworks
date:
---

工業Mod「Pipeworks」の解説ページです。

- toc
{:toc}

# Pipeworksとは

{% assign data = site.data.mods-industry.pipeworks %}
{% include details-mod.md %}

アイテムや水を輸送することを目的としたModです。また、輸送されたアイテムを使用する機械なども含まれています。
MeseconsやTechnic等を組み合わせることにより様々なことが可能となるModです。

ここでは主にアイテムの輸送に関連するアイテムを紹介します。

# 依存しているMod

MeseconsとDigilinesに依存していますが、無い場合は必要な機能は無効化されます。

# 追加されるアイテム

追加されるアイテムは大きく分けて３つの種類があります。

※ それぞれのレシピは他のModの影響によって変更されることがあるので、Unified Inventory等を使用して確認してください。

<dl>
  <dt>チューブ</dt>
  <dd>アイテムの輸送経路となる各種機能を備えたアイテムです。</dd>

  <dt>デバイス</dt>
  <dd>チューブの接続先となるアイテムです。アイテムの搬出、搬入されたアイテムの格納・使用等を行います。</dd>

  <dt>素材</dt>
  <dd>チューブの材料となる各種素材です。</dd>
</dl>

## チューブ

<dl>
  <dt>Pneumatic tube segment</dt>
  <dd>通常のチューブです。</dd>

  <dt>Accelerating Pneumatic Tube Segment</dt>
  <dd>このチューブは通過するアイテムの搬送速度を速めます。</dd>

  <dt>Conducting Pneumatic Tube Segment</dt>
  <dd>Mesecon信号を伝達することが出来るチューブです。</dd>

  <dt>Crossing Pneumatic Tube Segment</dt>
  <dd>
    このチューブを通過するアイテムは、曲がることなく全て直進します。
    チューブが存在しない等の理由で直進が出来ない場合、その場にアイテムがドロップされます。
    チューブを交差させる時に使用します。
  </dd>

  <dt>Detecting Pneumatic Tube Segment</dt>
  <dd>このチューブはアイテムが通過したときにMesecon信号を発信します。</dd>

  <dt>Digiline Detecting Pneumatic Tube Segment</dt>
  <dd>
    このチューブはアイテムが通過したときに指定されたChannelにDigiline信号を発信します。
    発信されるDigiline信号は<wbr>"Mod名:アイテム名 個数"という形式の文字列です。
  </dd>

  <dt>Vacuuming Pneumatic Tube Segment・Adjustable Vacuuming Pneumatic Tube Segment</dt>
  <dd>
    周囲にドロップされているアイテムを吸い込み搬送するチューブです。
    Vacuuming Pneumatic Tube Segmentは２ノード固定、Adjustable Vacuuming Pneumatic Tube Segmentは
    右クリックで表示された設定画面で最大８ノードの距離を指定することが出来ます。
  </dd>

  <dt>Sorting Pneumatic Tube Segment</dt>
  <dd>
    右クリックで表示された設定画面の内容に従い、アイテムの仕分けを行うチューブです。
    また、ON/OFFを上手く設定することによりアイテムの搬送経路を制御することも出来ます。
    仕分けは次のように行われます。
    <br><br>
    1. スイッチがONの方向が仕分け先候補に選別されます。<br>
    2. 仕分け先候補の中に搬送されてきたアイテムが登録されている場合、その仕分け先に決定します。<br>
    3. アイテムが登録されていない場合、何も登録されていない仕分け先候補全てが選択されます。<br>
    4. 3で選択された候補の中から優先順位を元に仕分け先を決定します。<br>
    5. 仕分け先が決定出来なかった場合、その場にアイテムがドロップされます。
  </dd>

  <dt>One way tube</dt>
  <dd>
    一方通行のチューブです。矢印の方向にのみアイテムの搬送が可能となります。
    逆流させた場合はその場にアイテムがドロップされます。
  </dd>

  <dt>High Priority Tube Segment</dt>
  <dd>
    搬送の優先順位(後述)が高いチューブです。主に搬送経路を固定したいときに使用します。
    Sorting Pneumatic Tube Segmentでも同様な処理は可能ですが、こちらの方が処理が軽くなります。
  </dd>
 
  <dt>Teleporting Pneumatic Tube Segment</dt>
  <dd>
    アイテムを別のTeleporting Pneumatic Tube Segmentに転送するチューブです。
    右クリックで設定画面を表示し、チャンネルと受信の許可を設定出来ます。
    この中を通過したアイテムは同じチャンネルで受信が許可されているチューブへと転送されます。
    受信が許可されているチャンネルが複数存在する場合、転送先はランダムに選択されます。
    転送先が存在しない場合はその場にアイテムがドロップされます。
  </dd>

  <dt>Airtight steelblock embedded tube / Airtight panel embedded tube</dt>
  <dd>
    鉄ブロックやパネルの中をPneumatic tube segmentが通っています。
    主に壁や床にチューブを通したいときに使用します。
  </dd>
</dl>

## デバイス

<dl>
  <dt>Autocrafter</dt>
  <dd>
    設定されたレシピに従って自動的にアイテムをクラフトします。
    クラフトを行うためにはレシピの登録と材料のセット、そしてスイッチをONにする必要があります。
    それぞれのインベントリーの説明は以下のとおりとなります。

    <dl>
      <dt>左上(３＊３スロット)</dt>
      <dd>ここにクラフトしたいアイテムのレシピを登録します。</dd>

      <dt>レシピの隣(１スロット)</dt>
      <dd>登録されたレシピに対応するアイテムが表示されます。</dd>

      <dt>右上(４＊３スロット)</dt>
      <dd>ここにクラフトされた生成物が保存されます。</dd>

      <dt>中央(８＊３スロット)</dt>
      <dd>ここに材料をセットします。</dd>
    </dl>

    チューブによって搬入されたアイテムは材料用のインベントリーへ搬入されます。
    また、Filter-Injectorによって生成物の搬出が可能です。
  </dd>

  <dt>Itemwise Filter-Injector / Stackwise Filter-Injector</dt>
  <dd>
    初期状態では左隣にあるノードのインベントリー(以下対象ノード)からアイテムを抽出し、チューブに搬出するデバイスです。
    ItemwiseとStackwiseの違いは搬出されるアイテムの個数です。
    Itemwiseは１つずつ、Stackwiseは指定された個数単位に纏めて搬出します。
    <br><br>
    Stackwiseでの個数の指定方法は、Prefer item typesに登録したアイテムの個数となりますが、
    アイテムが未登録、または個数が１の場合は１スタック全てが対象となります。
    また、Exact matchがONの時に対象ノードのアイテムの個数が不足している場合は搬出しません。
    個数チェックは対象ノード内の同一アイテムの合計でなく、各スタック単位でのチェックなので注意してください。
    <br><br>
    抽出されるアイテムは以下の方法で選択されます。<br>
    1. Prefer item typesの設定を元に、抽出対象となるアイテムの候補を選出します。<br>
    Prefer item typesが未設定の場合、全てのアイテムを抽出対象候補とします。<br>
    2. 次に、設定されたモードに基づいて対象ノードのスロットを検索します。
    モードは以下の３種類です。<br>
    <ul>
      <li>Sequence slots by Priority: 左上のスロットから検索します。</li>
      <li>Sequence slots Randomly:    ランダムに検索します。</li>
      <li>Sequence slots by Rotation: 左上のスロットから検索し、搬出後は次のスロットから検索を再開します。</li>
    </ul>
    3. 検索したスロットのアイテムが抽出対象かつ搬出個数の条件を満たしている場合、そのアイテムを搬出します。
    条件を満たしていない場合、次のスロットから検索を続けます。<br>
    4. 全てのスロットを検索し、アイテムが存在しない場合はなにも搬出しません。
    <br><br>
    このデバイスはMesecon信号、及び左クリックにより動作を行います。
  </dd>

  <dt>Digiline Filter-Injector</dt>
  <dd>
    受信したDigiline信号を元にアイテムを搬出するデバイスです。
    LuaController等と組み合わせて使用します。
    アイテム抽出のロジックはStackwise Filter-Injectorと同一となります。
    <br><br>
    Digiline信号の詳細についてはソースファイルやgitのログを参考にしてください。
    以下に例をあげておきます。

    <dl>
      <dt>単純な文字列による指定</dt>
      <dd>
        <pre><code class="lua">
"default:wood 2" -- default:woodが2個
        </code></pre>
      </dd>

      <dt>テーブルによる指定その１</dt>
      <dd>
        <pre><code class="lua">
{
  exmatch=false,      -- Exact matchがOFF
  "default:wood 2",   -- default:woodが2個
  "default:pine_wood" -- default:pine_woodが1個
}
          </code></pre>
      </dd>

      <dt>テーブルによる指定その２</dt>
      <dd>
        <pre><code class="lua">
{
  slotseq="random",              -- Sequence slots Randomly
  nofire=false,                  -- nofireがtrueの場合、アイテムを搬出しない
  exmatch=true,                  -- Exact matchがON
  {name="default:wood",count=2}, -- default:woodが2個
  {name="default:pine_wood"},    -- default:pine_woodが1スタック全部
  {group="wood", count=3}        -- woodグループのものが3個
}
        </code></pre>
      </dd>
    </dl>

    このデバイスはDigiline信号により動作を行います。
  </dd>

  <dt>Node Breaker</dt>
  <dd>
    正面にあるノードを破壊し、チューブに搬出するデバイスです。
    ノードを破壊するときに使用するアイテムは標準ではMesePickAxeが、プレイヤーによってセットされた
    アイテムが存在する場合は、そのアイテムの使用を試みます。
    このデバイスはMesecon信号により動作を行います。
  </dd>

  <dt>Deployer</dt>
  <dd>
    内部に保持しているアイテムを正面に設置するデバイスです。
    設置するアイテムは３＊３のスロットの左から右へ、上から下へと選択されます。
    チューブを使用することによりアイテムの補充が可能です。
    このデバイスはMesecon信号により動作を行います。
  </dd>

  <dt>Dispenser</dt>
  <dd>
    内部に保持しているアイテムをドロップするデバイスです。
    このデバイスはMesecon信号により動作を行います。
  </dd>

  <dt>Trash Can</dt>
  <dd>ゴミ箱です。中に入れられたアイテムは即座に消去されるので注意してください。</dd>

  <dt>Furnace / Chest / Locked Chest</dt>
  <dd>
    上記のMinetest標準アイテムはチューブによる搬入とFilter-Injectorによる搬出に対応出来るように拡張されます。<br>
    Furnaceは燃料の搬入は底面から、素材の搬入はそれ以外からとなります。
  </dd>
</dl>

## 素材

<dl>
  <dt>Oil extract</dt>
  <dd>各種木の葉から抽出されたオイルです。Unprocessed paraffinの材料となります。</dd>

  <dt>Unprocessed paraffin</dt>
  <dd>Oil extractをかまどで処理することにより作成されるアイテムです。Plastic sheetの材料となります。</dd>

  <dt>Plastic sheet</dt>
  <dd>Unprocessed paraffinをかまどで処理することにより作成されるアイテムです。各種チューブの材料となります。</dd>
</dl>

# チューブとデバイスの優先順位について

全てのチューブとデバイスには搬送の優先順位が存在します。
搬送中のアイテムが存在するチューブに複数のチューブやデバイスが接続されている場合、接続されているものの中で
一番優先順位が高い方向にアイテムが搬送されます。
一番優先順位が高いものが複数存在した場合は、それぞれに均等に振り分けられます。

例えば、一番優先順位が高いものが３つ（それぞれをABCとする）接続されている場合、一つ目の搬送アイテムがAに、
二つ目の搬送アイテムがBに、三つ目の搬送アイテムがCに、四つ目のアイテムがAという具合に振り分けられます。
アイテムのスタックが分割されるわけでは無いので注意してください。

チューブの優先順位は基本が50となり、One way tubeが75、そしてHigh Priority Tube Segmentが150となります。
また、デバイスはTrash Canを除き全て100となります。Trash Canの優先順位は1で最下位となります。
