## conda
1. 有关开发环境
   ```
   conda activate <envs>  //<>为参数
   conda deactivate <envs>
   conda info --envs                            //查看已经有的环境信息
   conda create --name <envs> --clone base      //基于已有的 base 环境（即默认环境）新建开发环境
   conda remove --name <envs> --all              //删除开发环境
   ```

2. 在指定环境下安装模块
    conda activate <envs>
    pip install <module>


