# Push和Pull

push与pull是两种数据通信方式，在Consumer从Broker获取消息过程中会用到这两种方式，区别如下：

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"><b>Push</b>
      </th>
      <th style="text-align:left"><b>Pull</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x6570;&#x636E;&#x4F20;&#x8F93;&#x72B6;&#x6001;</td>
      <td style="text-align:left">&#x4FDD;&#x5B58;&#x5728;Broker&#x7AEF;</td>
      <td style="text-align:left">&#x4FDD;&#x5B58;&#x5728;Consumer&#x7AEF;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x4F20;&#x8F93;&#x5931;&#x8D25;&#xFF0C;&#x91CD;&#x8BD5;</td>
      <td style="text-align:left">Broker&#x9700;&#x8981;&#x7EF4;&#x62A4;&#x6BCF;&#x6B21;&#x4F20;&#x8F93;&#x72B6;&#x6001;&#xFF0C;&#x9047;&#x5230;&#x5931;&#x8D25;&#x60C5;&#x51B5;&#x9700;&#x8981;&#x91CD;&#x8BD5;</td>
      <td
      style="text-align:left">&#x4E0D;&#x9700;&#x8981;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6570;&#x636E;&#x4F20;&#x8F93;&#x5B9E;&#x65F6;&#x6027;</td>
      <td style="text-align:left">&#x975E;&#x5E38;&#x5B9E;&#x65F6;</td>
      <td style="text-align:left">
        <ol>
          <li>&#x9ED8;&#x8BA4;&#x7684;&#x77ED;&#x8F6E;&#x8BE2;&#x65B9;&#x5F0F;&#x5B9E;&#x65F6;&#x6027;&#x4F9D;&#x8D56;pull&#x95F4;&#x9694;&#x65F6;&#x95F4;&#xFF0C;&#x95F4;&#x9694;&#x8D8A;&#x5927;&#x5B9E;&#x65F6;&#x6027;&#x8D8A;&#x4F4E;&#x3002;</li>
          <li>&#x957F;&#x8F6E;&#x8BE2;&#x6A21;&#x5F0F;&#x5B9E;&#x65F6;&#x6027;&#x4E0E;push&#x4E00;&#x81F4;&#x3002;</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6D41;&#x63A7;&#x673A;&#x5236;</td>
      <td style="text-align:left">Broker&#x9700;&#x8981;&#x4F9D;&#x636E;Consumer&#x7684;&#x6D88;&#x8D39;&#x80FD;&#x529B;&#x505A;&#x6D41;&#x63A7;&#x3002;</td>
      <td
      style="text-align:left">Consumer&#x53EF;&#x4EE5;&#x6839;&#x636E;&#x81EA;&#x8EAB;&#x6D88;&#x8D39;&#x80FD;&#x529B;&#x51B3;&#x5B9A;&#x662F;&#x5426;&#x53BB;pull
        message&#x3002;</td>
    </tr>
  </tbody>
</table>