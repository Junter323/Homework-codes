**C# **華氏與攝氏 轉換
進度
```
public partial class Form1 : Form
{
    String keyWorld = "abcdefghijklmnopqrstuvwxyz";
    public Form1()
    {
        InitializeComponent();
    }
    private void button1_Click(object sender, EventArgs e)
    {
        if (string.IsNullOrEmpty(textBox1.Text))
        {
            MessageBox.Show("錯誤！請輸入數值", "錯誤！", MessageBoxButtons.OK, MessageBoxIcon.Exclamation);
            return;
        }
        else
        {
            for (int i = 0; i < keyWorld.Length; i++)
            {
                if (textBox1.Text.Contains(keyWorld.Substring(i, 1)) || textBox1.Text.Contains(keyWorld.ToUpper().Substring(i, 1)))
                {
                    MessageBox.Show("請輸入正確數值", "錯誤！",MessageBoxButtons.OK, MessageBoxIcon.Error);
                    textBox1.Clear();
                    return;
                }
            }
            double ct, ft;
            ct = Convert.ToDouble(textBox1.Text);
            ft = (9.0 * ct) / 5.0 + 32;
            textBox2.Text = ft.ToString();
            label5.Text = "==>";
            button2.Enabled = false;
            textBox2.Enabled = false;
        }
    }

        private void Form1_Load(object sender, EventArgs e)
        {
            
        }

        private void button2_Click(object sender, EventArgs e)
        {
            if (string.IsNullOrEmpty(textBox2.Text))
            {
                MessageBox.Show("錯誤！請輸入數值", "錯誤！", MessageBoxButtons.OK, MessageBoxIcon.Exclamation);
                return;
            }
            else
            {
                for (int i = 0; i < keyWorld.Length; i++)
                {
                    if (textBox2.Text.Contains(keyWorld.Substring(i, 1)) || textBox2.Text.Contains(keyWorld.ToUpper().Substring(i, 1)))
                    {
                        MessageBox.Show("請輸入正確數值", "錯誤！",MessageBoxButtons.OK, MessageBoxIcon.Error);
                        textBox2.Clear();
                        return;
                    }
                }

                double ct, ft;
                ft = Convert.ToDouble(textBox2.Text);
                ct = (5.0 / 9.0) * (ft - 32);
                textBox1.Text = ct.ToString();
                label5.Text = "<==";
                button1.Enabled = false;
                textBox1.Enabled = false;
                label3.Visible = true;

            }
        }

        private void button3_Click(object sender, EventArgs e)
        {
            textBox1.Text = "";
            textBox2.Text = "";
            label5.Text = "";

            textBox1.Enabled = true;
            textBox2.Enabled = true;

            button1.Enabled = true;
            button2.Enabled = true;

            textBox1.Focus();
        }

        private void button4_Click(object sender, EventArgs e)
        {
            DialogResult Result = MessageBox.Show("您確定要關閉嗎?", "離開確認", MessageBoxButtons.OKCancel, MessageBoxIcon.Question);
            if (Result == DialogResult.OK)
            {
                MessageBox.Show("謝謝光臨", "哭，你走吧！", MessageBoxButtons.OK, MessageBoxIcon.Information);
                Application.Exit();
            }
            else if (Result == DialogResult.Cancel)
            {
          
            }
        }
    }
```
    
程式碼將有錯誤！請自行修正。 Copyright © 2020 Junter.Inc All Rights Reserved
