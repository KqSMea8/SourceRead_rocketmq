# RocketMQ与Apache Kafka的区别

表格 61RocketMQ与Kafka区别

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"><b>Apache Kafka</b>
      </th>
      <th style="text-align:left"><b>RocketMQ</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x961F;&#x5217;&#x6570;</td>
      <td style="text-align:left">&#x961F;&#x5217;&#xFF08;&#x5206;&#x533A;&#xFF09;&#x8FC7;&#x591A;&#x4F1A;Load&#x5347;&#x9AD8;</td>
      <td
      style="text-align:left">&#x5355;&#x673A;10&#x4E07;&#x4EE5;&#x4E0A;</td>
    </tr>
    <tr>
      <td style="text-align:left">SATA&#x76D8;&#x4E0B;&#x6027;&#x80FD;</td>
      <td style="text-align:left">&#x6027;&#x80FD;&#x6781;&#x4F4E;</td>
      <td style="text-align:left">&#x7531;&#x4E8E;PAGECACHE&#x4F5C;&#x7528;&#xFF0C;&#x4EE5;&#x53CA;&#x5237;&#x76D8;&#x65B9;&#x5F0F;&#x7684;&#x4E0D;&#x540C;&#xFF0C;&#x6027;&#x80FD;&#x63A5;&#x8FD1;SAS&#x76D8;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x670D;&#x52A1;&#x7AEF;&#x6D88;&#x606F;&#x8FC7;&#x6EE4;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;&#xFF0C;&#x5E76;&#x4E14;&#x5728;&#x670D;&#x52A1;&#x7AEF;&#x652F;&#x6301;&#x4E0E;&#x6216;&#x8868;&#x8FBE;&#x5F0F;&#x8FC7;&#x6EE4;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6309;&#x7167;&#x65F6;&#x95F4;&#x56DE;&#x6EAF;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;</td>
    </tr>
    <tr>
      <td style="text-align:left">Consumer&#x8BA2;&#x9605;&#x5B9E;&#x65F6;&#x6027;</td>
      <td style="text-align:left">1&#x3001;&#x6570;&#x636E;&#x843D;&#x76D8;&#x540E;&#xFF0C;&#x624D;&#x53EF;&#x88AB;&#x8BA2;&#x9605;
        <br
        />2&#x3001;Consumer Pull&#x6700;&#x5927;&#x95F4;&#x9694;&#x65F6;&#x95F4;</td>
      <td
      style="text-align:left">
        <p>1&#x3001;&#x6570;&#x636E;&#x8FDB;&#x5165;Broker&#xFF0C;&#x53EA;&#x8981;&#x5199;&#x5165;Pagecache&#xFF0C;&#x5373;&#x4F7F;&#x6CA1;&#x6709;&#x5237;&#x76D8;&#xFF0C;&#x4E5F;&#x53EF;&#x4EE5;&#x88AB;&#x8BA2;&#x9605;
          <br
          />2&#x3001;Consumer&#x91C7;&#x7528;&#x957F;&#x8F6E;&#x8BE2;&#x65B9;&#x5F0F;&#xFF0C;&#x5B9E;&#x65F6;&#x6027;&#x540C;Push&#x65B9;&#x5F0F;&#x4E00;&#x81F4;</p>
        <p>&#x7EFC;&#x4E0A;&#xFF0C;RocketMQ&#x6D88;&#x606F;&#x5EF6;&#x65F6;&#x975E;&#x5E38;&#x4F4E;&#xFF0C;&#x5B9E;&#x6D4B;&#x5728;&#x5E73;&#x5747;10ms&#x4EE5;&#x5185;</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5F02;&#x6B65;&#x5237;&#x76D8;&#x5B9E;&#x65F6;&#x6027;</td>
      <td style="text-align:left">&#x6309;&#x7167;&#x6761;&#x6570;&#x4E0E;&#x65F6;&#x95F4;&#x5237;&#x76D8;&#xFF0C;&#x5B9E;&#x65F6;&#x6027;&#x4F4E;</td>
      <td
      style="text-align:left">&#x540E;&#x53F0;&#x7EBF;&#x7A0B;&#x5B9E;&#x65F6;&#x5237;&#x76D8;&#xFF0C;&#x5237;&#x76D8;&#x51E0;&#x4E4E;&#x65E0;&#x5EF6;&#x65F6;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x540C;&#x6B65;&#x5237;&#x76D8;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;&#xFF0C;&#x4E14;&#x6027;&#x80FD;&#x63A5;&#x8FD1;&#x5F02;&#x6B65;&#x5237;&#x76D8;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5F02;&#x6B65;&#x590D;&#x5236;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x540C;&#x6B65;&#x53CC;&#x5199;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;&#xFF0C;&#x4E14;&#x6027;&#x80FD;&#x63A5;&#x8FD1;&#x5355;&#x5199;&#x4E00;&#x4E2A;Broker</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6D88;&#x606F;&#x67E5;&#x8BE2;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;&#xFF0C;&#x652F;&#x6301;&#x6309;&#x7167;&#x6D88;&#x606F;ID&#x3001;&#x6D88;&#x606F;key&#x67E5;&#x8BE2;&#x6D88;&#x606F;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5206;&#x5E03;&#x5F0F;&#x4E8B;&#x52A1;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5B9A;&#x65F6;&#x6D88;&#x606F;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x670D;&#x52A1;&#x7AEF;&#x6D88;&#x606F;&#x91CD;&#x8BD5;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5355;&#x961F;&#x5217;&#x5E76;&#x884C;&#x6D88;&#x8D39;</td>
      <td style="text-align:left">&#x4E0D;&#x652F;&#x6301;</td>
      <td style="text-align:left">&#x652F;&#x6301;</td>
    </tr>
  </tbody>
</table>

