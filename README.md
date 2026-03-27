# PL0
1. pl0.raw是清华大学编译原理第二版配套源码
2. pl0.flex.bison
   来自 https://github.com/Aman-4-Real/PL0_Compiler
3. pl0.test测试代码
4. EBNF

<img width="512" height="222" alt="image" src="https://github.com/user-attachments/assets/7e28795f-3dcc-4806-9736-6c90d34e10c0" />
<img width="972" height="918" alt="image" src="https://github.com/user-attachments/assets/d2e47cf5-6be2-4e6a-8ac7-eb8e8b22245d" />
<img width="1336" height="852" alt="image" src="https://github.com/user-attachments/assets/8c9ed5d4-2faa-46a8-be65-2ef6384ffca3" />
5. 词法分析DFA
<img width="1124" height="1080" alt="image" src="https://github.com/user-attachments/assets/810cf838-df99-4ac5-81bf-55dbda2ea34e" />
<img width="785" height="690" alt="image" src="https://github.com/user-attachments/assets/a594eebc-3800-4cc5-aeff-fab969150e75" />
6. 语法分析
<img width="887" height="503" alt="image" src="https://github.com/user-attachments/assets/e58c1811-b999-4bd0-ae24-b384950b5bc9" />


<program>     ::= <block> .
<block>       ::= [ "const" <ident> = <number> {, <ident> = <number>} ; ]
                 [ "var" <ident> {, <ident>} ; ]
                 { "procedure" <ident> ; <block> ; }
                 <statement>
<statement>   ::= <ident> := <expression>
                 | "begin" <statement> {; <statement>} "end"
                 | "if" <condition> "then" <statement>
                 | "while" <condition> "do" <statement>
<expression>  ::= [ + | - ] <term> { ( + | - ) <term> }
<term>        ::= <factor> { ( * | / ) <factor> }
<factor>      ::= <ident> | <number> | ( <expression> )
<condition>   ::= <expression> ( = | # | < | <= | > | >= ) <expression>

7. https://github.com/lotabout/write-a-C-interpreter
8. https://github.com/qing-2/PL0-Compiler
9. https://www.cnblogs.com/qrxqrx/articles/9084845.html
10. https://www.cnblogs.com/hesse-summer/p/12903005.html

11. 编写连接器
    *.o文件中的重定向信息，如何被重组的。

12. 基于flex,bison完成PL/0

13. 写一个支持自举的c语言编译器


14. 实验A
1.      编译原理系列 实验一词法分析 
        https://www.cnblogs.com/hesse-summer/p/12902891.html
2.      
        编译原理系列 实验二自上而下语法分析 
        https://www.cnblogs.com/hesse-summer/p/12902938.html

3.      编译原理系列 实验三自下而上语法分析
        https://www.cnblogs.com/hesse-summer/p/12902966.html

4.      编译原理系列 实验四语义分析与中间代码生成
        https://www.cnblogs.com/hesse-summer/p/12903005.html

15. 实验B

        进阶练习：编译器功能扩充
        在完成基础编译器后，你可以通过添加新特性来挑战更复杂的编译技术。这就像给你的编译器“打补丁”和“升级”。

1.
        扩充一：语法糖与控制流
                增加 if-then-else 语句：
                挑战点： 修改语法分析，处理 else 分支。这会引出经典的“悬空 else (dangling else)”歧义问题，你需要思考并实现解决方案（例如，让 else 总是与最近的 if 匹配）。

                增加 for 循环：
                挑战点： for 循环可以看作一个语法糖。你需要在语义分析阶段，将其“翻译”成等价的 while 循环结构（包含初始化、条件判断和增量），这涉及到更复杂的中间代码生成和跳转标签管理。

                增加 repeat-until 循环：
                挑战点： 这是一种“先执行，后判断”的循环。你需要设计新的控制流，生成与 while 循环镜像对称的中间代码，确保循环体至少执行一次。

2.
        扩充二：数据结构与类型系统
                支持数组：
                挑战点： 这是技术上的一个制高点。你需要：

                修改语法，支持 array 声明和下标访问 a[i]。
                扩充符号表，记录数组的维度、边界和类型。
                在代码生成时，将 a[i] 翻译成“基地址 + 偏移量”的地址计算指令。
                增加复合赋值运算符：
                挑战点： 实现 +=, -=, ++, -- 等。你需要区分 ++i (前缀) 和 i++ (后缀) 在语义上的细微差别（先加后用 vs 先用后加），并生成正确的代码。

3.
        扩充三：工程化与优化
                支持注释：
                挑战点： 在词法分析阶段，增加对 /* ... */ 或 // 注释的识别和忽略。这考验你设计词法分析器状态机的能力。

                改进符号表：
                挑战点： 将基础的线性查找符号表，升级为哈希表 (Hash Table) 实现。你需要设计哈希函数、处理哈希冲突，并管理作用域的进入和退出，这能极大提升大型程序的编译效率。

                增加指针支持 (高阶挑战)：
                挑战点： 引入 & (取地址) 和 @ (解引用) 运算符。这要求你重构整个类型系统，区分普通变量和指针变量，并在运行时处理内存地址的合法性校验，是迈向真实高级语言的关键一步。
