### 安装
```shell script
pip install gvcode
```

### 例子
```python
from gvcode import VFCode



if __name__ == '__main__':
    vc = VFCode(
        width=200,                       # 图片宽度
        height=80,                       # 图片高度
        fontsize=50,                     # 字体尺寸
        font_color_values = [
                '#ffffff',
                '#000000',
                '#3e3e3e',
                '#ff1107',
                '#1bff46',
                '#ffbf13',
                '#235aff'
            ],                           # 字体颜色值
        font_background_value='#ffffff', # 背景颜色值
        draw_dots=False,                 # 是否画干扰点
        dots_width=1,                    # 干扰点宽度
        draw_lines=True,                 # 是否画干扰线
        lines_width=3,                   # 干扰线宽度
        mask=False,                      # 是否使用磨砂效果
        font='arial.ttf'                 # 字体 内置可选字体 arial.ttf calibri.ttf simsun.ttc
    )
    # 验证码类型
    # 自定义验证码
    # vc.generate('abcd')

    # 数字验证码（默认5位）
    # vc.generate_digit()
    # vc.generate_digit(4)

    # 字母验证码（默认5位）
    # vc.generate_alpha()
    # vc.generate_alpha(5)

    # 数字字母混合验证码（默认5位）
    # vc.generate_mix()
    # vc.generate_mix(6)

    # 数字加减验证码（默认加法）
    vc.generate_op()
    # 数字加减验证码（加法）
    # vc.generate_op('+')
    # 数字加减验证码（减法）
    # vc.generate_op('-')

    # 图片字节码
    # print(vc.get_img_bytes())
    # 图片base64编码
    print(vc.get_img_base64())
    # 保存图片
    vc.save()
```