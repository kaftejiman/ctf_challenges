**Challenge**

Can you help me fix my grandfathers TV?

[Hi](https://refined-github-html-preview.kidonng.workers.dev/kaftejiman/ctf_challenges/raw/main/3k2021/helloworld/display_test.html)


**References**

I used the documents referenced below and fontforge for debugging.

  * [FontForge](https://fontforge.org/en-US/)
  * [The TrueType Instruction Set](https://docs.microsoft.com/en-us/typography/opentype/spec/tt_instructions)
  * [Instruction Set Summary](https://developer.apple.com/fonts/TrueType-Reference-Manual/RM07/appendixA.html)
  * [Challenge Font in XML text format](https://github.com/kaftejiman/ctf_challenges/blob/main/3k2021/base.xml)

**Input Check**

* Check function

```
      /* check function */
      PUSH[ ]
          43
      FDEF[ ]
          PUSH[ ]
              41
          CALL[ ] /* call setup */
          PUSH[ ]
              42
          CALL[ ] /* setup input, generate sums */
          PUSH[ ]
              44
          CALL[ ] /* call check on sums xor */
          PUSH[ ]
              0
          EQ[ ]
          IF[ ]
              PUSH[ ]
                  184 /* goto fail if 0 */
              JMPR[ ]
          EIF[ ]
          PUSH[ ]
            78
            0
          WCVTP[ ]
          PUSH[ ]
              70
              0
          WCVTP[ ] /* store i = 0 */
          PUSH[ ]
              71
              0
          WCVTP[ ] /* store a = 0 */
          PUSH[ ]
              72
              0
          WCVTP[ ] /* store b = 0 */
          PUSH[ ]
              73
              0
          WCVTP[ ] /* store c = 0 */
          PUSH[ ]
              74
              0
          WCVTP[ ] /* store d = 0 */
          PUSH[ ]
              75
              0
          WCVTP[ ] /* store e = 0 */
          CLEAR[ ] /* loop: jump back here */
          PUSH[ ]
              76
              0
          WCVTP[ ] /* store res = 0 */
          PUSH[ ]
            0
          PUSH[ ] 
              78
          RCVT[ ] /* get i */
          PUSH[ ]
              84
          LT[ ] 
          IF[ ] /* i lt 84 */
              PUSH[ ]
                78
              RCVT[ ]
              ADD[ ]
              PUSH[ ]
                  201
              ADD[ ] 
              DUP[ ] /* keep i */
              RCVT[ ]
              PUSH[ ]
                50
              ADD[ ] 
              RCVT[ ] /* sums[i] */
              PUSH[ ]
                  71
              SWAP[ ]
              WCVTP[ ] /* a = sums[i] */
              PUSH[ ]
                  1
              ADD[ ] /* i + 1 */
              DUP[ ] /* keep i + 1 */
              DUP[ ]
              RCVT[ ]
              PUSH[ ]
                50
              ADD[ ]
              RCVT[ ] /* sums[i] */
              PUSH[ ]
              DUP[ ] /* keep for res */
              PUSH[ ]
                  72
              SWAP[ ]
              WCVTP[ ] /* b = sums[i] */
              PUSH[ ]
                  71
              RCVT[ ] /* get a */
              PUSH[ ]
                  40
              CALL[ ] /* xor a and b */
              PUSH[ ]
                  76
              SWAP[ ]
              WCVTP[ ] /* res = a xor b */
              PUSH[ ]
                0
              PUSH[ ]
                78
              RCVT[ ]
              ADD[ ]
              PUSH[ ]
                  2
              ADD[ ] /* i + 2 */
              PUSH[ ]
                201
              ADD[ ]
              DUP[ ] /* keep i + 2 */
              RCVT[ ]
              PUSH[ ]
                50
              ADD[ ]
              RCVT[ ] /* sums[i] */
              DUP[ ]
              PUSH[ ]
                  73
              SWAP[ ]
              WCVTP[ ] /* c = sums[i] */
              PUSH[ ]
                  76
              RCVT[ ] /* read res */
              PUSH[ ]
                  40
              CALL[ ] /* res ^ c */
              PUSH[ ]
                  76
              SWAP[ ]
              WCVTP[ ] /* c = res ^ c */
              PUSH[ ]
                0
              PUSH[ ]
                78
              RCVT[ ]
              ADD[ ]
              PUSH[ ]
                  3
              ADD[ ] /* i + 3 */
              PUSH[ ]
                201
              ADD[ ]
              DUP[ ] /* keep i + 3 */
              RCVT[ ]
              PUSH[ ]
                50
              ADD[ ]
              RCVT[ ] /* sums[i] */
              DUP[ ]
              PUSH[ ]
                  74
              SWAP[ ]
              WCVTP[ ] /* d = sums[i] */
              PUSH[ ]
                  76
              RCVT[ ] /* read res */
              PUSH[ ]
                  40
              CALL[ ] /* res ^ d */
              PUSH[ ]
                  76
              SWAP[ ]
              WCVTP[ ] /* res = res ^ d */
              PUSH[ ]
                0
              PUSH[ ]
                78
              RCVT[ ]
              ADD[ ]
              PUSH[ ]
                  4
              ADD[ ] /* i + 4 */
              PUSH[ ]
                201
              ADD[ ]
              DUP[ ] /* keep i + 4 */
              RCVT[ ]
              PUSH[ ]
                50
              ADD[ ]
              RCVT[ ] /* sums[i] */
              DUP[ ]
              PUSH[ ]
                  75
              SWAP[ ]
              WCVTP[ ] /* e = sums[i] */
              PUSH[ ]
                  76
              RCVT[ ] /* read res */
              PUSH[ ]
                  40
              CALL[ ] /* res ^ e */
              PUSH[ ]
                  76
              SWAP[ ]
              WCVTP[ ] /* res = res ^ e */
              PUSH[ ]
                0
              PUSH[ ]
                78
              RCVT[ ]
              ADD[ ]
              PUSH[ ]
                  5
              ADD[ ] /* i + 5 */
              PUSH[ ]
                201
              ADD[ ]
              RCVT[ ] /* input xor value */
              PUSH[ ]
                  76
              RCVT[ ]
              EQ[ ]
              IF[ ]
                  PUSH[ ]
                      70
                  RCVT[ ] /* get i */
                  PUSH[ ]
                      1
                  ADD[ ] /* i + 1 */
                  DUP[ ]
                  PUSH[ ]
                      70
                  SWAP[ ]
                  WCVTP[ ] /* i = i + 1 */
                  PUSH[ ]
                    6
                  PUSH[ ]
                    28
                  CALL[ ] /* fix */
                  MUL[ ]
                  PUSH[ ]
                    78
                  SWAP[ ]
                  WCVTP[ ] /* get table indice */
                  PUSH[ ]
                      -196 /* go back to loop */
                  JMPR[ ]
              ELSE[ ]
                  PUSH[ ]
                      15
                  JMPR[ ]
              EIF[ ]
          ELSE[ ]
              /* correct: jump here */
              CLEAR[ ] /* cleanse stack */
              PUSH[ ]
                  1
              DUP[ ] /* exit with 1 in stack */
              PUSH[ ]
                  77
              SWAP[ ]
              WCVTP[ ] /* check_bit = 1 */
              PUSH[ ]
                  10 /* exit */
              JMPR[ ]
          EIF[ ]
          /* fail: jump here */
          CLEAR[ ] /* cleanse stack */
          PUSH[ ]
              0
          DUP[ ]
          PUSH[ ]
              77
          SWAP[ ] /* check_bit = 0 */
          WCVTP[ ]
      ENDF[ ]
```      


* Function 40 is the implementation of 

```python
lookup = [[0, 1], [1, 0]]

def xor(x , y):
    res = 0
    bit = 0
    while x != 0 or y != 0:
        xx = x // 2
        x_bit = x - xx*2 #get lsb of x
        yy = y // 2
        y_bit = y - yy*2 #get lsb of y
        tmp = lookup[x_bit][y_bit]
        for _ in range(bit):
            tmp *= 2
        res += tmp
        x //= 2
        y //= 2
        bit += 1
    return res
```

**Flag generation**

```python

flag = '3k{hope_it_was_fun_to_soulv}'

while i <= len(flag)/2-1:
    csts.append(ord(flag[i*2])*256 + ord(flag[i*2+1]))
    i = i + 1

for cnt in range(1, 15):
    i = random.randint(0, 13)
    j = random.randint(0, 13)
    k = random.randint(0, 13)
    l = random.randint(0, 13)
    m = random.randint(0, 13)
    target = csts[i] ^ csts[j] ^ csts[k] ^ csts[l] ^ csts[m]
    print("[{}, {}, {}, {}, {}, {}],".format(i, j, k, l, m, target), end='')
```

* Target constraints

```
#==> TARGET: [13163, 31592, 28528, 25951, 26996, 24439, 24947, 24422, 30062, 24436, 28511, 29551, 30060, 30333]
cvt: .. constraints ..
201: [12, 10, 6, 10, 11, 26480]
207: [1, 4, 1, 0, 1, 8567],
213: [7, 9, 11, 11, 0, 13177],
219: [13, 0, 3, 9, 2, 4173],
225: [9, 0, 5, 6, 3, 14148],
231: [3, 8, 8, 10, 9, 21876],
237: [0, 9, 3, 4, 2, 3908],
243: [7, 11, 0, 2, 0, 17273],
249: [7, 13, 2, 4, 6, 20076],
255: [7, 2, 8, 0, 13, 110],
261: [7, 0, 8, 6, 2, 5984],
267: [6, 2, 9, 8, 9, 31597],
273: [9, 13, 5, 9, 9, 30334],
279: [5, 5, 11, 9, 6, 19816],


xor of targets = 32513
```

* Helper function puts correct flag in memory

```
      FDEF[ ] /* test function */
        PUSH[ ]
        100
        51
        WCVTP[ ]
        PUSH[ ]
        101
        107
        WCVTP[ ]
        PUSH[ ]
        102
        123
        WCVTP[ ]
        PUSH[ ]
        103
        104
        WCVTP[ ]
        PUSH[ ]
        104
        111
        WCVTP[ ]
        PUSH[ ]
        105
        112
        WCVTP[ ]
        PUSH[ ]
        106
        101
        WCVTP[ ]
        PUSH[ ]
        107
        95
        WCVTP[ ]
        PUSH[ ]
        108
        105
        WCVTP[ ]
        PUSH[ ]
        109
        116
        WCVTP[ ]
        PUSH[ ]
        110
        95
        WCVTP[ ]
        PUSH[ ]
        111
        119
        WCVTP[ ]
        PUSH[ ]
        112
        97
        WCVTP[ ]
        PUSH[ ]
        113
        115
        WCVTP[ ]
        PUSH[ ]
        114
        95
        WCVTP[ ]
        PUSH[ ]
        115
        102
        WCVTP[ ]
        PUSH[ ]
        116
        117
        WCVTP[ ]
        PUSH[ ]
        117
        110
        WCVTP[ ]
        PUSH[ ]
        118
        95
        WCVTP[ ]
        PUSH[ ]
        119
        116
        WCVTP[ ]
        PUSH[ ]
        120
        111
        WCVTP[ ]
        PUSH[ ]
        121
        95
        WCVTP[ ]
        PUSH[ ]
        122
        115
        WCVTP[ ]
        PUSH[ ]
        123
        111
        WCVTP[ ]
        PUSH[ ]
        124
        117
        WCVTP[ ]
        PUSH[ ]
        125
        108
        WCVTP[ ]
        PUSH[ ]
        126
        118
        WCVTP[ ]
        PUSH[ ]
        127
        125
        WCVTP[ ]
      ENDF[ ]
```
