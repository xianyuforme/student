# student
计G191 2019322184 张国琦
==============
实验目的：1、分析学生选课系统  2、使用GUI窗体及其组件设计窗体界面  3、完成学生选课过程业务逻辑编程  4、基于文件保存并存取数据  5、处理异常

实验要求：1、设计GUI窗体，支持学生注册、课程新加、学生选课、学生退课、打印学生选课列表等操作。
         2、基于事件模型对业务逻辑编程，实现在界面上支持上述操作。
         3、针对操作过程中可能出现的各种异常，做异常处理。
         4、基于输入、输出编程，支持学生、课程、教师等数据的读写操作。
         5、基于Github.com提交实验，包括实验SRC源文件程序、README.MD实验报告文档。

#JAVA
--------------------------------
实验过程:

	1、创建窗体类public class ManagerFrame extends JFrame {·····}
        2、创建面板容器public class CoursePanel extends JPanel {·····}
                  创建对象JTable，JButton，CardLayout，JTextField，JPanel，JComboBox，JLabel
                  创建主功能区监听器
                           刷新监听、选课监听、退课监听
                        ```java
                            public void ····(ActionEvent e) {····
                                    }
                                    ```
                         退课监听逻辑：
                     ```Java   
                         jb2.addActionListener(new ActionListener() {
			@Override
			public void actionPerformed(ActionEvent e) {
				if (jtable.getSelectedRows().length == 0) {
					JOptionPane.showMessageDialog(null, "请先选择一条选课记录!");
				} else {
					if (JOptionPane.showConfirmDialog(null, "确定要删除选定的课程吗?") == 0)
						try {
							deleteCourseByTable();
							refresh();
						} catch (Exception e1) {
							e1.printStackTrace();
						}

				}
			}
		});
               ```
        3、文件输入输出并于置入按钮操作
               文件输入
               ```java
                jbAddSummit.addActionListener(new ActionListener() {

			@Override
			public void actionPerformed(ActionEvent e){
			                 ····
                                            ····
                                            //创建与之前相对应的属性并排序
				String strbuffer=cid+" "+user+" "+name+" "+teacher+" "+xuefen+"\n";				
		        try {
		        	FileWriter writer = new FileWriter("````", true);
		        	writer.write(strbuffer);
		        	writer.flush();
		        	writer.close();
		        	initData();
		        } catch (IOException e2) {
		            e2.printStackTrace();
		        }
				JOptionPane.showMessageDialog(null, "添加成功!");
				jtfAddCid.setText(null);
				jtfAddUser.setText(null);
				jtfAddXuefen.setText(null);
				card.first(jpanelAll);
			}
		});
                  ```
                  文件输出
                 ```java
                  FileReader ····· = new FileReader(·····);
                  BufferedReader ·····= new BufferedReader(·····);
                  ```  
                  逻辑：
                 ```java
                 String eachLine = null;//定义每一行
		while((eachLine = br.readLine()) != null){
			String[] temp = eachLine.split(" ");
			Vector<String> row = new Vector<String>();
			for(int i = 0; i < temp.length; i++){
				row.add(temp[i]);
			}
			rowData.add(row);
		}
                 ```
         4、创建测试

实验流程图
----------------------
.............
/.....
..

运行结果图
------------------
![mingzi](图片链接)
实验感想
---------------------
                                    
