# ��ϰ7�����������һЩ����

> ԭ�ģ�[Exercise 7: More Variables, Some Math](http://c.learncodethehardway.org/book/ex7.html)

> ���ߣ�[����](https://github.com/wizardforcel)

�����ͨ������`int`��`float`��`char`��`double`���͵ı�����������������������飬����������Ϥ���ǰɡ����������ǻ��ڸ�����ѧ���ʽ��ʹ�����ǣ������һ��������C�Ļ�������������

```
int main(int argc, char *argv[])
{
    int bugs = 100;
    double bug_rate = 1.2;

    printf("You have %d bugs at the imaginary rate of %f.\n",
            bugs, bug_rate);

    long universe_of_defects = 1L * 1024L * 1024L * 1024L;
    printf("The entire universe has %ld bugs.\n",
            universe_of_defects);

    double expected_bugs = bugs * bug_rate;
    printf("You are expected to have %f bugs.\n",
            expected_bugs);

    double part_of_universe = expected_bugs / universe_of_defects;
    printf("That is only a %e portion of the universe.\n",
            part_of_universe);

    // this makes no sense, just a demo of something weird
    char nul_byte = '\0';
    int care_percentage = bugs * nul_byte;
    printf("Which means you should care %d%%.\n",
            care_percentage);

    return 0;
}
```

��������һС����������뱳���������飺

����ex7.c:1-4

����C�����ͨ����ʼ��

����ex7.c:5-6

����ΪһЩα���bug����������һ��`int`��һ��`double`������

����ex7.c:8-9

������ӡ������������û��ʲô�¶�����

����ex7.c:11

����ʹ����һ���µ�����`long`������һ�������ֵ�������Դ���Ƚϴ������

����ex7.c:12-13

����ʹ��`%ld`��ӡ�������������������˸����η���`%d`���档��ӵ�"l"��ʾ�������������δ�ӡ��

����ex7.c:15-17

����ֻ�Ǹ������������ʹ�ӡ��

����ex7.c:19-21

������׫��һ�����bug�ʵ�����������ļ���ǳ�����ȷ������ǳ�С����������Ҫʹ��`%e`�Կ�ѧ����������ʽ��ӡ����

����ex7.c:24

������������﷨`'\0'`������һ���ַ�������������һ�������ֽڡ��ַ���ʵ����������0��

����ex7.c:25

����ʹ������ַ�����bug����������������0����Ϊ���ж���������Ҫ���ĵġ��Ľ�����������չʾ������ʱ�������ĳ�ª������

����ex7.c:26-27

����������ӡ������ע����ʹ����`%%`�������ٷֺţ�����ӡһ��`%`�ַ���

����ex7.c:28-30

����`main`�����Ľ�β��

��һ�δ���ֻ�Ǹ���ϰ������ʾ������������㡣�������Ҳչʾ�����������C�п�������������������û�еļ��ɡ�����C��˵��һ�����ַ���ͬʱҲ��һ����������Ȼ����С������ȷ��ˡ�����ζ������Զ������������㣬�����Ǻ��ǻ�����������Ҳ���������ġ�

�����һ�����У����һ�μ���C���������ֱ�ӷ��ʻ����ġ����ǻ��ں�����½������롣

## ��ῴ��ʲô

ͨ������Ӧ�ÿ������������

```
$ make ex7
cc -Wall -g    ex7.c   -o ex7
$ ./ex7
You have 100 bugs at the imaginary rate of 1.200000.
The entire universe has 1073741824 bugs.
You are expected to have 120.000000 bugs.
That is only a 1.117587e-07 portion of the universe.
Which means you should care 0%.
$
```

## ���ʹ������

��֮ǰһ������`printf`�������Ĳ�����ʹ���������Ա�`%c`����������ʹ��`%s`����ӡ`nul_byte`����ʱ�ᷢ��ʲô��������Щ֮����`Valgrind`���������������������γ��Ի����ʲô��

## ������

+ ��Ϊ`universe_of_defects`��ֵ������Ϊ��ͬ�Ĵ�С���۲�������ľ��档
+ ��Щ�޴������ʵ���ϴ�ӡ����ʲô��
+ ��`long`��Ϊ`unsigned long`���������ҵ�������˵̫������֡�
+ ��������`unsigned`����ʲô��
+ �����Լ����ͣ����¸���ϰ֮ǰ��Ϊʲô`char`���Ժ�`int`��ˡ�