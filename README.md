> 
> MY First Project

IPFInder: Used to display the required IP address of requested website
  
  
  
    




    import javax.swing.*;
    import java.awt.event.*; 
    import java.net.*;
    public class FindingIP extends JFrame implements ActionListener{
       JLabel l;
       JTextField tf;
       JButton b;
       //Creating a constructor 
       FindingIP(){
        super("IP Finder");
        l=new JLabel("Enter URL:");
        l.setBounds(50,70,150,20);;
        tf=new JTextField();
        tf.setBounds(50,100,200,20);
        b=new JButton("Find IP");
        b.setBounds(50,150,80,30);
        b.addActionListener(this);
        add(l);
        add(tf);
        add(b);
        setSize(300,300);
        setLayout(null);
        setVisible(true);
    }
   
//Crearting action events by making a class action performed

      public void actionPerformed(ActionEvent e){
        String url=tf.getText();
        try {
            InetAddress ia=InetAddress.getByName(url);
            String ip=ia.getHostAddress();
            JOptionPane.showMessageDialog(this,ip);
        } catch (UnknownHostException e1) {
            JOptionPane.showMessageDialog(this,e1.toString());
        }
    }
    public static void main(String[] args) {
        new FindingIP();
    }
    } 
   
 
