# C# 三位正整數比大小

> [name=Junter.wjs]
### 版本一


```csharp=
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            int n1, n2, n3;
            n1 = Convert.ToInt32(textBox1.Text);
            n2 = Convert.ToInt32(textBox2.Text);
            n3 = Convert.ToInt32(textBox3.Text);

            if (n1 >= n2)
            {
                if(n2>=n3)
                {
                    label5.Text = n1.ToString() + " >= " + n2.ToString() + " >= " + n3.ToString();
                }
                else
                {
                    if (n1>=n3)
                    {
                        label5.Text = n1.ToString() + " >= " + n3.ToString() + " >= " + n2.ToString();
                    }
                    else
                    {
                        label5.Text = n2.ToString() + " >= " + n1.ToString() + " >= " + n2.ToString();
                    }
                }
            }
            else
            {
                if (n1>=n3)
                {
                    label5.Text = n2.ToString() + " >= " + n1.ToString() + " >= " + n3.ToString();
                }
                else
                {
                    if (n2>=n3)
                    {
                        label5.Text = n2.ToString() + " >= " + n3.ToString() + " >= " + n1.ToString();
                    }
                    else
                    {
                        label5.Text = n3.ToString() + " >= " + n2.ToString() + " >= " + n1.ToString();
                    }
                }
            }
        }
    }
```


---

### 版本二
```csharp=
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            int n0, n1, n2;
            n0 = Convert.ToInt32(textBox1.Text);
            n1 = Convert.ToInt32(textBox2.Text);
            n2 = Convert.ToInt32(textBox3.Text);

            List<int> num = new List<int>();

            num.Add(n0);
            num.Add(n1);
            num.Add(n2);
            num.Sort();
            num.Reverse();

            label5.Text = num[0] + " >= " + num[1] + " >= " + num[2];
        }
    }
```
---

### 版本三
```csharp=
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            int n0, n1, n2;
            int min = 0, med = 0, max = 0;

            n0 = Convert.ToInt32(textBox1.Text);
            n1 = Convert.ToInt32(textBox2.Text);
            n2 = Convert.ToInt32(textBox3.Text);

            int[] nums = new int[] { n0, n1, n2 };

            for (int i = 0; i < 3; i++)
            {
                if (i == 0 || nums[i] > max)
                    max = nums[i];
                if (i == 0 || nums[i] < min)
                    min = nums[i];
            }
            for (int i = 0; i < 3; i++)
            {
                if (nums[i] != max && nums[i] != min)
                {
                    med = nums[i];
                    break;
                } else
                {
                    med = nums[i];
                    break;
                }
            }

            label5.Text = max + " >= " + med + " >= " + min;
        }
    }
```


:::warning  
程式碼將有錯誤！請自行修正。  
:::
 Copyright © 2020 Junter.wjs All Rights Reserve