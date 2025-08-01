<h1>Dự án được quản lý bởi Git và trong dự án có nhiều repo riêng</h1>

<p align="center">
  <img src="https://github.com/user-attachments/assets/3e81bd19-e0ed-4e4f-9176-126a9b9f0959" width="45%"/>
  <img src="https://github.com/user-attachments/assets/70e874f9-8417-47d4-9208-593fc82daeec" width="45%"/>
</p>

<h2>Dưới đây là một số câu lệnh làm việc với dự án có dạng submodule</h2>

<ol>
  <li>
    <p><strong>Duyệt qua tất cả các repo con và xem log:</strong></p>
    <pre><code>git submodule foreach "git log"</code></pre>
    <p>Mỗi repo con sẽ thực hiện lệnh <code>git log</code>.</p>
  </li>
  <li>
    <p><strong>Chuyển nhánh <code>dev</code> cho tất cả các submodule (nếu tồn tại):</strong></p>
    <pre><code>git submodule foreach "git checkout dev || :"</code></pre>
    <p>Lệnh này giúp chuyển sang nhánh <code>dev</code> nếu repo con có nhánh đó, nếu không thì bỏ qua mà không bị lỗi.</p>
  </li>
</ol>
