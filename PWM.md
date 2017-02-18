# ШИМ на ThinkPad

![](https://i.imgur.com/U9fUcGd.gif "Фак по ШИМу")

***
 
## Как проявляется/чем грозит?

Могут быстро уставать глаза. В долгосрочной перспективе – посадка зрения. У некоторых людей может вызывать даже головную боль. Плюс еще:
> They are especially harmful in models with LED backlight because the colors of the emitted light are not as inert as the colors of the CCFL backlight and so they reach high amplitudes and rapid luminance changes.

Однако мнения людей расходятся. Некоторые утверждают что работают на экранах с ШИМ и не чувствуют дискомфорта, тогда как от определенного монитора без ШИМ чувствуют усталость. Вероятно сказывается частота с которой экран мерцает. Ниже анон проясняет про психосоматику.

Тащемто, ШИМ до 2кГц влияет на лимбическую систему, от чего люди болеют. От простого недомогания до проблем с сердцем, давлением, желудком, мозгом, всем короче.

Само по себе мерцание на твой хрусталик никак влиять не может. Но может напрягать мозг, поднимать давление в том числе и внутриглазное. А там всякая глаукома и прочее. Но это только при условии что твой мозг замечает мерцание. Полная **психосоматика**.
 
**Что это вообще такое и как проверить свой экран?**
- [http://brinservice.com/bolyat-glaza-ot-komputera-monitora.html](http://brinservice.com/bolyat-glaza-ot-komputera-monitora.html)
 
***

## Варианты софтового "лечения":

**Под Windows**

- Частично помогает утилита IntelPWMControl ( исходники [http://pastebin.com/6iirMbfc](http://pastebin.com/6iirMbfc)) [https://youtu.be/ycKzTDnTYTQ](https://youtu.be/ycKzTDnTYTQ) (Испытано аноном на X220 и T520 (подробности ниже, в списке 500-ок))
 
**Под Linux**

- [https://devbraindom.blogspot.ru/2013/03/eliminate-led-screen-flicker-with-intel.html
](https://devbraindom.blogspot.ru/2013/03/eliminate-led-screen-flicker-with-intel.html)
- [https://wiki.archlinux.org/index.php/Backlight_(Русский)#Backlight_PWM_modulation_frequency_.28Intel_i915_only.29](https://wiki.archlinux.org/index.php/Backlight_(Русский)#Backlight_PWM_modulation_frequency_.28Intel_i915_only.29)
- Значения регистров меняем под свои! – Added "intel_reg_write 0xc8254 0x07a107a1" to /etc/rc.local to get 500 Hz PWM on Toshiba C850 (default is 200 Hz).
 
Для выяснения нужных регистров:
- Intel доки [https://01.org/linuxgraphics/documentation/driver-documentation-prms](https://01.org/linuxgraphics/documentation/driver-documentation-prms)
- Intel доки по sandy Brige [https://01.org/linuxgraphics/sites/default/files/documentation/snb_ihd_os_vol3_part3.pdf](https://01.org/linuxgraphics/sites/default/files/documentation/snb_ihd_os_vol3_part3.pdf)
 
Искать в гугле:
- Eliminate LED screen flicker with Intel i915
- backlight control in Linux
 
## Варианты аппаратного "лечения":

- Для X220/X230 помогает замена матрицы на FHD. См. ниже пункт для этих моделей;
- Махание хуем перед экраном/камерой не помогает. Анон проверил. 
 
***

## Перепись Thinkpad'ов:

**X1 Carbon GEN3 (FHD).** FAIL : ШИМ такой, что ловится просто переводом взгляда из угла в угол экрана. Полное говно во всех отношениях, кроме времени работы от батарейки, тача и веса.

**X1 Carbon GEN4 (FHD).** OK : Никакого мерцания не обнаружил, даже фотоаппаратом с выдержкой 1/8000. x1 с g710 на фоне [[пруф]](https://cloud.mail.ru/public/9qq8/jQEMwoKsz)
 
**X41t**
. OK : Проверено аноном с помощью фотоаппарата с выдержкой 1/8000 секунды.
 
**60-ки**

- T60. FAIL : [[пруф]](https://youtu.be/NKJhHK0bjpw)
- X60t. FAIL : 1024х768 Сообщил анон, правда без указания пруфа и методики тестирования
 
**200-ки**

- X201. FAIL: Шимка на моём х201 наблюдается только на средней яркости. На минимальной слабо заметна. На максимальной ШИМ вообще не заметен.
- X220 (IPS). FAIL: Карандашный тест анона и китайская мобила показали наличие ШИМ на яркости ниже 2/3. "Всегда сижу с выкрученной на 100 % яркостью, так что мне норм";
- X220 (IPS). FAIL: Это же подтверждается видео на ютубе [[пруф1]](https://youtu.be/apLyrzH-qNA) [[пруф2]](https://youtu.be/SpDdy9jSx7Y); еще хорошо видно на 9м30сек [[пруф3]](https://youtu.be/kOd0KFouWJY); 
- X220/X230. УСПЕШНОЕ ИСПРАВЛЕНИЕ: Существует вариант модификации с заменой матрицы на FHD IPS. [[пруф]](https://www.youtube.com/watch?v=9b_dJzbXf7A) Цена вопроса: 4800 руб (матрица) + 3500 (набор для модификации). Подробности [[здесь]](http://forum.thinkpads.com/viewtopic.php?f=43&p=792251);
- X230i (TN) : С момента покупки поставил частоту на 1000Hz, глаза не болят. Проверял карандашем и камерой. Ставил по инструкции [[пруф]](https://devbraindom.blogspot.ru/2013/03/eliminate-led-screen-flicker-with-intel.html)
 
**400-ки**

- T410. FAIL : [[пруф]](https://youtu.be/ycKzTDnTYTQ);
- T420. FAIL: 1366х768. Проверено фотоаппаратом: на 1/320 сек. уже появляются темные участки, на 1/400 сек. уже идут полосы
- T430. FAIL : (мотай на 11:20) [[пруф]](https://youtu.be/8LtMuZ4DQjQ);
- T430. FAIL : Анон снял [видео](https://cloud.mail.ru/public/EGvg/k7U5NPKRa);
- T440. OK : [[пруф]](https://cloud.mail.ru/public/M97n/UKD1boDuW)
- T460. OK :
  - Анон снял [видео](https://cloud.mail.ru/public/12ju/iEPyUtv2s) (на видео яркость с максимума до минимума убавил - разница незаметна, вероятно, из-за автокоррекции яркости в камере телефона, на который все снималось );
  - Проверено на [notebookcheck.net](http://www.notebookcheck.net/Lenovo-ThinkPad-T460p-Notebook-Review.160923.0.html)
- L450. FAIL : ШИМ на всем диапазоне яркости, кроме максимального (карандашный тест)
 
**500-ки**

- L510 (TN). FAIL : [Проверка анона](https://cloud.mail.ru/public/CfK2/Qqe94qjUs) с помощью фотоаппарата (выдержка 1/800). Яркость экрана средняя;
- T520. FAIL (УСПЕШНО ИСПРАВЛЕНО С ПОМОЩЬЮ intelPWNcontrol): [[пруф]](https://cloud.mail.ru/public/6Mj2/zbYVTp5UD);
- T530. FAIL. С ёбаматрицей тоже есть ШИМ. Анон проверял фотоаппаратом. Но частота высокая так что анон ШИМ не замечал.
 
***

## Другие мнения анонов:

- Сам сижу сейчас на ноуте с ШИМ-ящей матрицей. Вынужден выкручивать яркость на 13 из 15, ибо глазки вытекают от ШИМ. Готов даже к TN, но чтобы яркость можно было крутить без боли.
- А фликер фри (Flicker Fri) не означает отсутствие ШИМ-регулировки яркости. В половине фликерфри мониторов тот же ШИМ. ШИМ заметен только низкочастотный, когда совсем производитель мудак.
- Юзаю x201 (имеется ШИМ – прим.автора) Мне норм, работаю по 13 часов в день препод уже года два, дискомфорта нет. Зрительная гимнастика наше всё (seriously)
- У меня лично от слишком ШИМящего экрана (~200) при низком и среднем уровне подсветки мозг настолько ахуевает, что начинает троиться в глазах
- Тащемто, шим до 2кГц влияет на лимбическую систему, от чего люди болеют. От простого недомогания до проблем с сердцем давлением желудком мозгом всем короче, может и рак вызвать.
 
Ссылка на пасту: http://pastebin.com/ZRxfz3Ax