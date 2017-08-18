- [svg描边 demo地址](http://lianglovejie.com/svg/)

####首先获取svg的path路径

    在psd中直接选中图层获取右键复制svg  前提是你的图层有路径（svg path）
    
    
####添加css样式
    
    path {
            stroke-dasharray: 1010;
            stroke-dashoffset: 1010;
            animation: dash 3s linear;
            animation-fill-mode: forwards;
        }

        @keyframes dash {
            to {
                stroke-dashoffset: 0;
            }
        }
    