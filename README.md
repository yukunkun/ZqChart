#### ZqChart
##### 一个折线的view,有月份和日期的显示
#### 直接看图
  ![S70605-18053556.jpg](http://upload-images.jianshu.io/upload_images/3001453-f1e029ca963807ff.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
[使用方法](http://www.jianshu.com/writer#/notebooks/11842585/notes/12975631)
#### 布局文件    
     <com.example.cloud.zqchart.ZqChart
         android:id="@+id/chart"
         android:layout_width="match_parent"
         android:layout_height="wrap_content"/>
#### mainactivity中的使用         
    public class MainActivity extends AppCompatActivity {
        private ZqChart mchart;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
            mchart = (ZqChart) findViewById(R.id.chart);
            ArrayList<Chart> datas = new ArrayList<>();
    
            for (int i = 0; i < 12; i++) {
                for (int i1 = 0; i1 < 30; i1++) {
                    Chart chart=new Chart();
                    chart.dateDay= i1+1;
                    chart.dateMonth= i+1;
                    chart.money= new Random().nextInt(50)+100;
                    datas.add(chart);
                }
            }
            mchart.setDatas(datas);
        }
    }
