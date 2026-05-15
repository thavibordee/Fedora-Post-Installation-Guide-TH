✏️ หลังจาก Distro เจ้าดังอย่าง [<b>Fedora</b>](https://fedoraproject.org/) ปล่อยเวอร์ชันล่าสุด <b>Fedora 44</b> ออกมาให้บรรดาสาวกได้ดาวน์โหลด ติดตั้ง และใช้งานกันแล้วนั้น เชื่อได้ว่าไม่ว่าจะเป็น "มือเก่า" หรือ "มือใหม่" ก็ต้องเคยมีคำถามเกิดขึ้นว่า "จะทำอะไรต่อดี?" เพราะ Fedora เป็น Distro ที่ให้ความสำคัญอย่างมากในเรื่องของลิขสิทธิ์ เพราะฉะนั้นผู้ใช้งานจึงจำเป็นต้อง config หรือตั้งค่าเพิ่มเติมหลังจากที่ติดตั้ง Fedora ลงบนอุปกรณ์แล้ว เพื่อให้ตอบโจทย์การใช้งานของผู้ใช้แต่ละคนมากยิ่งขึ้น ซึ่งรีวิว หรือคู่มือส่วนใหญ่มักจะเป็นภาษาอังกฤษ ส่วนตัวเลยอยากทำเวอร์ชันคำอธิบายภาษาไทย เพื่อให้คนไทยที่สนใจอยากใช้งาน Linux สามารถนำไปตั้งค่า ตลอดจนประยุกต์ให้เหมาะกับความต้องการใช้งานของแต่ละคนได้ง่าย และสะดวกมากยิ่งขึ้นนะครับ
<p></p>
<b>หมายเหตุ:</b> ข้อมูลทั้งหมดนี้ไม่ใช่ข้อมูลที่เป็น Official จากทาง Fedora นะครับ แต่มาจากประสบการณ์การใช้งานส่วนตัว รวมถึงหาข้อมูลเพิ่มเติม และรวบรวมจากแหล่งต่าง ๆ ที่น่าเชื่อถือ และคิดว่าน่าจะเป็นประโยชน์กับผู้ใช้ส่วนใหญ่ไม่มากก็น้อย อย่างไรก็ตามการ config หรือตั้งค่าต่าง ๆ นี้ <b>หากเกิดข้อผิดพลาด หรือความเสียหายขึ้นแก่ผู้ที่นำไปใช้ ไม่ว่าจะเป็นทั้งในส่วนของข้อมูล หรืออุปกรณ์ต่าง ๆ ผมไม่ขอรับผิดชอบไม่ว่าในกรณีใด ๆ ทั้งสิ้น</b> เพราะฉะนั้นจึงอยากให้ทุกคนอ่านรายละเอียด และทำความเข้าใจ ก่อนที่จะนำคำสั่งต่าง ๆ ไปใช้งาน เพื่อหลีกเลี่ยง และป้องกันปัญหาที่อาจเกิดขึ้นได้
<p></p>
<hr></hr>
<b>💡 ข้อควรระวังเพิ่มเติมเกี่ยวกับคำสั่งต่าง ๆ หรือ commands</b>
<ul>
  <li>สำหรับคำสั่งที่ขึ้นต้นด้วยคำว่า <code>sudo</code> คือการใช้สิทธิ "run as admin" เพราะฉะนั้นจะมีการถาม password ให้เรากรอก  </li>
  <li>การพิมพ์กรอก password ใน Terminal จะไม่เห็น password หรือสัญลักษณ์ **** เวลาที่เราพิมพ์ แต่ไม่ต้องตกใจ ให้พิมพ์ต่อจนครบ แล้วค่อยกด enter</li>
  <li>ในชุดคำสั่งที่มี <code>-y</code> จะหมายถึงการตอบ yes หรือตอบตกลงในทุกกรณี </li>
  <li>เพื่อป้องกัน และหลีกเลี่ยงปัญหาที่มักจะเกิดขึ้นจากการพิมพ์คำสั่งไม่ถูกต้อง เช่น (พิมพ์เกิน หรือพิมพ์ตกหล่น) สามารถใช้การ copy + paste ได้ แต่อย่าลืมอ่านรายละเอียดให้ครบถ้วนก่อนนะครับ</li>
  <li>คำสั่งต่าง ๆ หรือ commands ที่สรุปมาให้นี้ ผมได้ลองทดสอบบน Fedora 43 และ Fedora 44 แล้ว ไม่พบปัญหาแต่อย่างใด เพราะอย่างที่ทราบกันดีว่าใน Fedora รุ่นใหม่ ตัว DNF5 ได้เปลี่ยน behavior หลายอย่าง และหลาย ๆ แพคเกจมีการแยกออกมาอย่างชัดเจน เพราะฉะนั้นคำสั่ง หรือ commands จึงมีการปรับ และตัดบางส่วนที่ไม่จำเป็นออกไป จากเดิมที่หลายคนคุ้นเคยนะครับ</li>
</ul>
<img width="800" height="450" alt="image" src="https://github.com/user-attachments/assets/6dec9aeb-730d-4802-b2bd-226a8d5619ea" />
<hr></hr>
<H3><b>เริ่มต้นด้วย RPM Fusion และ Terra</b></H3>
อย่างที่ทราบกันดีว่า Fedora เป็น Distro ที่ให้ความสำคัญในเรื่องของลิขสิทธิ์เป็นอย่างมาก เพราะฉะนั้นเราจึงจำเป็นต้องติดตั้ง RPM Fusion และ Terra ก่อน เพราะเป็นแหล่งที่รวบรวมแพคเกจ .rpm ทั้งแบบฟรี และไม่ฟรีเอาไว้อย่างมากมาย เช่น Steam, Discord, ไดรเวอร์, codecs สำหรับเปิดไฟล์เพลง และวีดีโอ รวมถึงอื่น ๆ อีกมากมาย
<p></p>
<b>สำหรับติดตั้ง Repository ที่ฟรี</b>
<pre>sudo dnf install -y \
  https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm</pre>
<b>สำหรับติดต้ัง Repository ที่ไม่ฟรี</b>
<pre>sudo dnf install -y \
  https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm</pre>
<i>(Optional)</i> <b>สำหรับติดตั้ง Terra</b> อันนี้จะติดตั้ง หรือไม่ก็ได้นะครับ เพราะบน Fedora 44 ตัว Terra repo ยังไม่ stable เท่ากับ RPM Fusion และมีบางแพคเกจที่ conflict กันอยู่ กรณีต้องการใช้งาน Terra แนะนำให้ติดตั้งเฉพาะแพคเกจที่จำเป็นเท่านั้น
<pre>sudo dnf install --nogpgcheck \
--repofrompath 'terra,https://repos.fyralabs.com/terra$releasever' \
terra-release</pre>
<b>สำหรับติดตั้ง App-Stream metadata</b>
<pre>sudo dnf install rpmfusion-free-appstream-data rpmfusion-nonfree-appstream-data
sudo dnf check-update</pre>
<p></p>
<hr></hr>
<H3><b>ต่อกันด้วยการ Updates</b></H3>
<p></p>
หลายคนอาจจะสงสัยว่าทำไมถึงต้องอัปเดตด้วย ทั้งที่เพิ่งจะลง OS ใหม่ นั่นก็เพราะว่าการลง OS ใหม่ มักจะมีแพคเกจที่เก่า หรือล้าหลังอยู่ด้วยนั่นเอง
<pre>sudo dnf update -y</pre>
⚠️ หลังจากอัปเดตแล้ว แนะนำให้ reboot เครื่องด้วยนะครับ
<p></p>
<blockquote>ข้อแนะนำ: อย่าลืม! ทำการอัปเดตเป็นประจำทุกสัปดาห์ (หรืออย่างน้อยเดือนละครั้ง)</blockquote>
<p></p>
<hr></hr>
<H3><b>การอัปเดต Firmwares</b></H3>
<p></p>
ให้การทำงานของฟีเจอร์ต่าง ๆ เช่น WiFi หรือการจัดการแบตเตอรีมีประสิทธิภาพมากยิ่งขึ้น จึงจำเป็นที่จะต้องอัปเดตเฟิร์มแวร์ เพื่อให้ฮาร์ดแวร์ของเครื่องเราได้รับเฟิร์มแวร์ล่าสุด
<p></p>
<b>ตรวจสอบว่ามีเฟิร์มแวร์อะไรบ้างที่งอัปเดตได้</b>
<pre>sudo fwupdmgr get-devices</pre>
<b>รีเฟรชฐานข้อมูลเฟิร์มแวร์</b>
<pre>sudo fwupdmgr refresh --force</pre>
<b>ตรวจสอบการอัปเดต</b>
<pre>sudo fwupdmgr get-updates</pre>
<b>ทำการอัปเดต</b>
<pre>sudo fwupdmgr update</pre>
⚠️ หลังจากอัปเดตเฟิร์มแวร์แล้ว แนะนำให้ reboot เครื่องด้วยนะครับ
<hr></hr>
<H3><b>เข้าถึง Software ต่าง ๆ ได้มากยิ่งขึ้น</b></H3>
<p></p>
<H3><b>#การตั้งค่า Flathub</b></H3>
<p></p>
โดยปกติแล้ว Fedora จะมาพร้อม Flatpak ที่เป็นเวอร์ชันทั่วไป ในขณะที่ Flathub คือแหล่งรวมแอปฯ ที่เป็นเวอร์ชันที่ใช้งานจริง เพราะฉะนั้นก่อนอื่นทำการลบ Fedora repo ที่ถูกจำกัด เพื่อป้องกันการเกิด Conflict ต่าง ๆ
<pre>flatpak remote-delete fedora</pre>
<p>ขั้นตอนต่อมา คือ การติดตั้ง Flathub ซึ่งผมได้แยกออกเป็นทั้งหมด 4 ทางเลือก ตามลักษณะของแอปฯ แต่ละประเภทนะครับ ผู้ใช้สามารถเลือกติดตั้งทางเลือกที่คิดว่าเหมาะกับตัวเองมากที่สุดได้เลยนะครับ</p>
<b>ทางเลือกที่ 1 - ติดตั้งแบบจัดเต็ม</b> ผู้ใช้จะสามารถเข้าถึงได้ทุก ๆ อย่าง (รวมถึงแอปฯ ที่ทางผู้พัฒนาเลิกพัฒนาอย่างเป็นทางการด้วยนะครับ)
<pre>flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo</pre>
<b>ทางเลือกที่ 2 - ติดตั้งได้เฉพาะแอปฯ ที่ผ่านการตรวจสอบ และรับรองแล้วเท่านั้น</b> เฉพาะแอปฯ ที่ใช้ได้จริง โดยยังอยู่ในความดูแลของทางผู้พัฒนา
<pre>flatpak remote-add --if-not-exists --subset=verified flathub https://flathub.org/repo/flathub.flatpakrepo</pre>
<b>ทางเลือกที่ 3 - ติดตั้งได้เฉพาะแอปฯ ที่ฟรี และเป็นโอเพ่นซอร์สเท่านั้น</b> เฉพาะแอปฯ ฟรีที่เป็นโอเพ่นซอร์สเท่านั้น
<pre>flatpak remote-add --if-not-exists --subset=floss flathub https://flathub.org/repo/flathub.flatpakrepo</pre>
<b>ทางเลือกที่ 4 - ติดตั้งได้ทั้งแอปฯ ที่ผ่านการรับรอง และแอปฯ ฟรีที่เป็นโอเพ่นซอร์ส</b> เป็นทางเลือกที่รวมทั้งแบบที่ 2 และ 3 เข้าไว้ด้วยกัน
<pre>flatpak remote-add --if-not-exists --subset=verified_floss flathub https://flathub.org/repo/flathub.flatpakrepo</pre>
<hr></hr>
<H3><b>การรองรับไฟล์ AppImage</b></H3>
<p></p>
อาจมีบางแอปฯ ที่ทางผู้พัฒนาทำออกมาเป็นไฟล์ AppImage จึงจำเป็นต้องติดตั้ง FUSE เพื่อให้รองรับ และสามารถใช้งานไฟล์ AppImage ได้
<pre>sudo dnf install -y fuse fuse-libs</pre>
<i>(Optional)</i> ตัวจัดการไฟล์ AppImage (สามารถติดตั้งเพื่อความสะดวกในการจัดการไฟล์ AppImage ได้ง่ายมากยิ่งขึ้น)
<pre>flatpak install -y flathub it.mijorus.gearlever</pre>
<hr></hr>
<H3><b>การรองรับไฟล์ที่ถูกบีบอัด</b></H3>
<p></p>
เมื่อต้องการแตกไฟล์ที่ถูกบีบอัดมา เช่น ไฟล์ <code>.rar</code>
<pre>sudo dnf install -y p7zip p7zip-plugins unrar</pre>
<hr></hr>
<H3><b>การติดตั้งไดรเวอร์ด้านกราฟิก</b></H3>
<p></p>
<b>สำหรับเครื่องที่ใช้การ์ดจอ NVIDIA</b>
<p></p>
<b>การตั้งค่าข้อกำหนดเบื้องต้น</b> (ทั้งกรณีที่ Secure Boot ตั้งค่าไว้เป็น Enabled และ Disabled)
<p></p>
<p>ติดตั้ง kernel และเครื่องมือต่าง ๆ</p>
<pre>sudo dnf install kernel-devel kernel-headers gcc make dkms acpid libglvnd-glx libglvnd-opengl libglvnd-devel pkgconfig</pre>
<p>สำหรับการ์ดจอ RTX4000+ ให้ใช้คำสั่งนี้ในการตั้งค่า</p>
<pre>sudo sh -c 'echo "%_with_kmod_nvidia_open 1" > /etc/rpm/macros.nvidia-kmod'</pre>
<p></p>
📌 <b>กรณีที่ Secure Boot ตั้งค่าไว้เป็น Enabled</b> <i>(แนะนำ)</i>
<p>ให้ทำการติดตั้ง signing tools ก่อนที่จะติดตั้งไดรเวอร์</p>
<pre>sudo dnf install akmods mokutil openssl
sudo kmodgenca -a
sudo mokutil --import /etc/pki/akmods/certs/public_key.der</pre>
<p>ทำการ reboot เครื่อง แล้วลงทะเบียน MOK Key (ตั้ง password) และค่อย reboot เครื่องอีกรอบ</p>
<p>ติดตั้งไดรเวอร์</p>
<pre>sudo dnf install akmod-nvidia xorg-x11-drv-nvidia-cuda</pre>
<p>รอประมาณ 5-15 นาทีในการติดตั้ง แล้วค่อยทำการ reboot เครื่อง</p>
📌 <b>กรณีที่ Secure Boot ตั้งค่าไว้เป็น Disabled</b> 
<p>ให้ทำการตั้งค่า Secure Boot เป็น Disabled ใน Bios ให้เรียบร้อยก่อน</p>
<p>ทำการติดตั้ง</p>
<pre>sudo dnf install akmod-nvidia xorg-x11-drv-nvidia-cuda</pre>
<p>รอจนติดตั้งเรียบร้อย และค่อยทำการ reboot เครื่อง</p>
<b>ตรวจสอบการติดตั้ง</b>
<p>ผลลัพธ์การตรวจสอบ จะแจ้งสถานะของไดรเวอร์ และ Secure Boot</p>
<pre>nvidia-smi
modinfo nvidia
mokutil --sb-state </pre>
<hr></hr>
<b>สำหรับเครื่องที่ใช้การ์ดจอ AMD และ Intel</b>
<p></p>
<p>ติดตั้งแพคเกจหลัก (สำหรับทั้ง AMD และ Intel) เพื่อช่วยให้การทำงานดียิ่งขึ้น</p>
<pre>sudo dnf install mesa-vulkan-drivers vulkan-loader mesa-libGLU libva-utils</pre>
<b>ติดตั้งตัวช่วยเร่งประสิทธิภาพการแสดงผลสำหรับ AMD</b>
<pre>sudo dnf swap mesa-va-drivers mesa-va-drivers-freeworld mesa-vdpau-drivers mesa-vdpau-drivers-freeworld</pre>
<b>ติดตั้งตัวช่วยเร่งประสิทธิภาพการแสดงผลสำหรับ Intel</b>
<p></p>
<p>สำหรับ Intel ตั้งแต่ gen 11 ขึ้นไป</p>
<pre>sudo dnf install -y intel-media-driver</pre>
<p>สำหรับ Intel ที่เก่ากว่า gen 11</p>
<pre>sudo dnf install -y libva-intel-driver</pre>
<hr></hr>
<H3><b>เติมเต็มด้านความบันเทิง และมัลติมีเดียต่าง ๆ</b></H3>
<b>Codecs สำหรับไฟล์วิดีโอ</b> อย่างที่ทราบกันดีว่า Fedora จะให้ความสำคัญกับเรื่องลิขสิทธิ์ จึงไม่ได้มีการใส่ Codecs มาให้แต่แรก ผู้ใช้จึงจำเป็นต้องติดตั้งเพิ่มเติม เพื่อให้เติมเต็มการใช้งานด้านมัลติมีเดียมากยิ่งขึ้น
<p></p>
<p>ใช้งาน FFmpeg ตัวเต็ม</p>
<pre>sudo dnf swap ffmpeg-free ffmpeg --allowerasing</pre>
<p></p>
<p>อัปเดตไฟล์ด้านมัลติมีเดีย (GStreamer ตัวเต็ม + Codecs)</p>
<pre>sudo dnf update @multimedia --setopt="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin</pre>
<p></p>
<p>(Optional) ติดตั้งแอปฯ และปลั๊กอินเพิ่มเติมสำหรับไฟล์เสียง และวิดีโอ</p>
<pre>sudo dnf groupupdate sound-and-video</pre>
<hr></hr>
<H3><b>การปรับเร่งประสิทธิภาพด้านฮาร์ดแวร์</b></H3>
<p></p>
<p>จะเป็นการปรับให้ระบบใช้งาน GPU เป็นหลักเพื่อลดภาระ และการทำงาน CPU ของเครื่องลง</p>
<pre>sudo dnf install -y ffmpeg-libs libva libva-utils</pre>
<p></p>
<p>สำหรับเครื่องที่ใช้การ์ดจอ NVIDIA ให้ติดตั้งคำสั่งนี้เพิ่มด้วย</p>
<pre>sudo dnf install -y libva-nvidia-driver</pre>
<hr></hr>
<H3><b>แก้ปัญหาเรื่องไฟล์วิดีโอที่เกิดขึ้นเวลาใช้งานบน Firefox</b></H3>
<p></p>
<p>ติดตั้ง add-ons นี้ เพื่อแก้ปัญหาไฟล์วิดีโอ H.264 ที่เกิดขึ้น</p>
<pre>sudo dnf install -y openh264 gstreamer1-plugin-openh264 mozilla-openh264
sudo dnf config-manager --set-enabled fedora-cisco-openh264
sudo dnf update -y</pre>
<blockquote>⚠️ หลังจากติดตั้ง add-ons แล้ว ให้ restart ตัว Firefox ด้วยนะครับ</blockquote>
<hr></hr>
<H3><b>แก้ปัญหาเรื่องเวลา สำหรับผู้ใช้ที่ทำ Dual Boot</b></H3>
<p>สำหรับผู้ใช้ที่ติดตั้งทั้ง Windows และ Linux แต่มีปัญหาเรื่องเวลาที่แสดงผลไม่ถูกต้อง</p>
<pre>sudo timedatectl set-local-rtc 0 --adjust-system-clock</pre>
<hr></hr>
<H3><b>เคลียร์ไฟล์ต่าง ๆ ที่ไม่จำเป็น เพื่อให้เครื่องของคุณไม่รกไปด้วยไฟล์ขยะเก่า ๆ</b></H3>
<b>System Cleanup</b>
<p>เคลียแคช และแพคเกจเก่าที่ไม่ได้ถูกใช้งานแล้วออกจากเครื่อง</p>
<pre>sudo dnf clean all
sudo dnf autoremove -y</pre>
<hr></hr>
<p></p>
👏 สำหรับใครที่ตั้งค่าตามคำสั่งต่าง ๆ มาจนถึงบรรทัดนี้ <b>ขอแสดงความยินดีด้วยนะครับ คุณตั้งค่าเบื้องต้นเสร็จสิ้นเป็นที่เรียบร้อยแล้ว</b> หลังจากนี้จะเป็นการตั้งค่า ติดตั้ง และปรับแต่งเพิ่มเติม ขึ้นอยู่กับลักษณะการใช้งาน และความชอบของแต่ละคนนะครับ จะลองตั้งค่า และติดตั้งตามหรือไม่ก็ได้ครับ
<hr></hr>
<H3><b>ข้อความ error ระหว่างหน้า Boot Screen</b></H3>
<p>ถึงแม้ว่าปัญหานี้จะไม่ได้ส่งผลกระทบต่อการใช้งานโดยตรง และพบในผู้ใช้งานบางคนเท่านั้น แต่ก็เป็นปัญหาที่สร้างความหงุดหงิดให้หลาย ๆ คนที่ต้องเจอกับข้อความ error ในตอนที่เปิดเครื่อง หรือว่า reboot เครื่องทุกครั้ง สำหรับข้อความ error ที่ปรากฏขึ้น คือ</p>
<code>error: ../../grub-core/commands/loadenv.h:read_envblk_file:51:invalid environment block.</code>
<p></p>
<p>จากข้อความ error ข้างต้น พอจะสรุปได้ว่าเกิดปัญหาที่ไฟล์ที่ใช้เก็บค่าตั้งต้นของ Bootloader (GRUB) เสียหายครับ โดยมีขั้นตอน และวิธีการแก้ไข ดังนี้</p>
<p></p>
<b>1. ทำการลบไฟล์ที่เสียหาย</b>
<pre>sudo rm -f /boot/grub2/grubenv</pre>
<p></p>
<b>2. สร้างไฟล์ที่แก้ไขแล้วขึ้นมาใหม่</b>
<pre>sudo grub2-editenv /boot/grub2/grubenv create</pre>
<p></p>
<b>3. ตรวจเชคความถูกต้องของไฟล์ที่เราสร้างในข้อ 2.</b> (โดยไฟล์ที่ถูกต้อง เมื่อเราใส่คำสั่งด้านล่างแล้ว จะปรากฏผลลัพธ์เป็นกลุ่ม # จำนวนหนึ่ง)
<pre>cat /boot/grub2/grubenv</pre>
<p></p>
<b>4. อัปเดตไฟล์ที่เราตั้งค่า</b>
<pre>sudo grub2-mkconfig -o /boot/grub2/grub.cfg</pre>
<p></p>
<p>เมื่อทำครบทั้ง 4 ข้อแล้ว ลอง reboot เครื่องดูนะครับ ข้อความ error ก็จะไม่ปรากฏขึ้นอีกในหน้า Boot Screen</p>
<hr></hr>
<H3><b>ปรับค่าความโปร่งแสงของหน้าต่าง Terminal</b></H3>
<p>อันนี้ออกแนวเป็นความชอบส่วนตัวนะครับ ปกติแล้วเวลาเราเรียกใช้งาน Terminal จะมาเป็นหน้าต่างสีดำทึบ พร้อมคำสั่งที่เป็นตัวอักษรวิ่งไล่ลงมา แต่ถ้าใครรู้สึกอึดอัด เราสามารถปรับตั้งค่าให้หน้าต่างดังกล่าวมีความโปร่งใสมากขึ้น สามารถมองทะลุไปยังหน้าต่างที่อยู่ด้านหลังได้ แต่ก็ยังสามารถมองเห็นโค้ดคำสั่งได้ชัดเจนอยู่ (ในที่นี้จะตั้งค่าความโปร่งแสงไว้ที่ 10% นะครับ >> 1 - 0.10 = 0.90)</p>
<pre>gsettings set org.gnome.Ptyxis.Profile:/org/gnome/Ptyxis/Profiles/$PTYXIS_PROFILE/ opacity .90</pre>
<hr></hr>
<H3><b>ว่าด้วยเรื่องของการ Backup</b></H3>
<p>สำหรับการ Backup บน Linux จะแบ่งออกเป็น 2 แบบนะครับ คือ</p>
<b>1. การ Backup ในส่วนของไฟล์ระบบ</b> อย่างที่ทราบกันดีว่า Linux เป็นระบบปฏิบัติการที่เราสามารถปรับเปลี่ยนได้เกือบจะทุกอย่าง และมีบ่อยครั้งที่เรา(ซน)ปรับจนทำให้ระบบล่ม หรือแม้แต่การอัปเดตบางครั้งก็อาจจะมี bug และทำให้ระบบล่มได้เช่นกัน ดังนั้นการ Backup ไฟล์ของระบบไว้ จึงเป็นมาตรการที่ช่วยให้เรายังสามารถใช้งานต่อได้ ไม่ว่าจะเกิดปัญหาอะไรขึ้นก็ตาม
<p></p>
<p><b>Snapshots</b> จะเป็นตัวช่วยสำคัญในการ backup และจัดการไฟล์ของระบบ สำหรับผู้ใช้ที่ฟอร์แมตเป็น btrfs (ค่า default ของ Fedora ตั้งแต่ตอนติดตั้ง)</p>
<pre>sudo dnf install -y btrfs-assistant btrbk snapper</pre>
<p>กรณีต้องการตั้งค่าให้ทำการ backup อัตโนมัติ</p>
<pre>sudo systemctl enable --now snapper-timeline.timer
sudo systemctl enable --now snapper-cleanup.timer</pre>
<p></p>
<b>2. การ Backup ไฟล์ และข้อมูลส่วนตัว</b> ในส่วนนี้จะเป็นการ backup ไฟล์ และข้อมูลต่าง ๆ ของเรา เช่น รูปภาพ เอกสาร และอื่น ๆ ที่ไม่ใช่ไฟล์ระบบนะครับ
<p></p>
<p>โดยเราจะใช้ <b>Déjà Dup</b> ช่วยในการ backup ไฟล์ และข้อมูลส่วนตัวต่าง ๆ ของเรา</p>
<pre>sudo dnf install -y deja-dup</pre>
<p></p>
<blockquote>💡 ข้อแนะนำ: การ backup แนะนำให้ backup ไว้บน ext.harddisk หรือ cloud มากกว่านะครับ ไม่แนะนำให้ backup ไว้บน disk เดียวกันกับไฟล์ต้นฉบับ</blockquote>
<hr></hr>
<H3><b>ของเล่นปรับแต่งหน้าจอ</b></H3>
<p>Fedora Workstation มาพร้อม DE (Desktop Environment) แบบ GNOME ซึ่งขึ้นชื่อในเรื่องของความ minimal ที่หลาย ๆ คนชื่นชอบ และอีกหลาย ๆ คนก็ไม่ชอบ เพราะมันดูเหมือนไม่มีอะไรเลย แต่อย่างที่เราทราบกันดีว่า Linux สามารถปรับแต่ง หรือจัดการอย่างไรก็ได้เท่าที่เราจะนึก(โค้ดคำสั่ง)ออก แต่ถ้าปรับมากไปก็อาจทำให้พังได้ ผมเลยเลือกเอาของเล่นเฉพาะที่น่าสนใจ และมี feedback จากผู้ใช้ส่วนใหญ่ไปในทางที่ดีนะครับ ซึ่งถือเป็นการคัดกรอง และลดความเสี่ยงลงระดับนึงครับ</p>
เริ่มกันที่ <b>GNOME Tweaks</b> ช่วยให้เราสามารถเพิ่ม/ลดปุ่มต่าง ๆ รวมถึงปรับแต่งแถบต่าง ๆ ได้
<p></p>
<pre>sudo dnf install -y gnome-tweaks</pre>
<p></p>
ต่อกันด้วย <b>Extension Manager</b> เป็นเครื่องมืออเนกประสงค์ที่จะช่วยให้เราสามารถค้นหา และติดตั้ง GNOME Shell Extension ต่าง ๆ ได้
<p></p>
<pre>flatpak install -y flathub com.mattjakeman.ExtensionManager</pre>
<p></p>
<p>สำหรับ extension ที่แนะนำเบื้องต้นนะครับ</p>
<ul>
  <li><b>Vitals</b> แสดงค่าการใช้ซีพียู/แรม (และค่าอื่น ๆ) แบบเรียลไทม์ไว้ที่แถบด้านบนหน้าจอ</li>
  <li><b>Dash to Dock</b> เปลี่ยน Dock แบบเดิม ให้ตอบโจทย์การใช้งานมากยิ่งขึ้น</li>
  <li><b>Blur my Shell</b> ช่วยปรับให้หน้าจอดูมีมิติมากขึ้น โดยปรับมุมหน้าต่างให้มีความโค้งมนมากยิ่งขึ้น</li>
</ul>
<p></p>
<p>ส่วนอันนี้สำหรับใครที่ลง Fedora KDE Plasma Desktop จะแนะนำให้ลง <b>Latte Dock</b> ที่จะทำให้การใช้งาน Dock คล้ายกับ Mac OS</p>
<p></p>
<pre>sudo dnf install -y latte-dock</pre>
<hr></hr>
<H3><b>เปลี่ยนชื่อคอมพิวเตอร์ของคุณ</b></H3>
<p>จากค่าเริ่มต้นที่ชื่อว่า fedora เราสามารถเปลี่ยนชื่อให้เป็นชื่ออื่นได้ตามที่เราต้องการ ซึ่งเราจะเห็นชื่อนี้บ่อย ๆ เวลาที่เราเปิด Terminal ขึ้นมา แล้วเราต้องพิมพ์โค้ดคำสั่งต่อหลังชื่อผู้ใช้@ชื่อคอมพิวเตอร์นั่นเอง</p>
<p></p>
<pre>sudo hostnamectl set-hostname ชื่อคอมพิวเตอร์ที่ต้องการเปลี่ยน</pre>
<hr></hr>
