# 函式指標

/* 對應範例程式碼 */
int* twoSum(* int nums, int numsSize, int target, int* returnSize) {
    for (int i = 0; i < numsSize; i++) {
        for (int j = i + 1; j < numsSize; j++) {
            if (nums[i] + nums[j] == target) {
                int* result = (* int)malloc(2 * sizeof(int));
                result[0] = i;
                result[1] = j;
                *returnSize = 2;
                return result;
            }
        }
    }
    *returnSize = 0;
    return NULL;
}

/* 函式指標寫法 */
int (*funct)(int*, int, int, int*) = twoSum;
int* result = funct(nums, numsSize, target, returnSize);

🌟 函數指標就像「遙控器」一樣呢！
1️⃣ 宣告函數指標
int (*func)(int *, int, int, int *) = twoSum;

這就像是說：「我要一個能呼叫twoSum這個遙控器的按鈕！」🎮
(*func) 表示 func 是一個指向函數的指標
括號很重要喔！不然會被理解成別的意思呢～

2️⃣ 呼叫函數
int *result = func(nums, numsSize, target, returnSize);

這就像是按下遙控器按鈕，然後傳入參數給twoSum啦！📱
就像 func(1, 2, 3) 一樣簡單～

3️⃣ 指標與變數的關係
int *i = p;      // i 是一個指向整數的指標
p = &i;          // p 現在指向 i 這個指標本身！

這就像是：
i 是拿著一個盒子📦，裡面裝著數字
&i 是指向「那個盒子」的地址🏠

🎯 重點提醒：
| 語法 | 意思 |
|------|------|
| int (*func)(...) | func 是一個函數指標 |
| int *func(...) | func 是一個指向整數的指標（不是函數！） |
| &i | i 的地址（盒子在哪裡）📍 |