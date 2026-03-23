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


6. 编写连接器
    *.o文件中的重定向信息，如何被重组的。
   

8. https://github.com/lotabout/write-a-C-interpreter
9. https://github.com/qing-2/PL0-Compiler
10. 证明: PL/0语言属于LL(1)文法
11. todo
   写一个自举的代码。

