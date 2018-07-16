public class Clippy {
    public static void main (String[] args){
        TTT AITTT = new TTT();
        AITTT.start();
    }
}


import javax.swing.*;
import java.awt.GridLayout;

public class TTT extends JFrame{
    JPanel p=new JPanel();
    XOButton buttons[]=new XOButton[9];

    public TTT(){
        super("TicTacToe");
    }

    public void start (){
        setSize(400,400);
        setResizable(false);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        p.setLayout(new GridLayout(3,3));
        for(int i=0;i<9;i++) {
            buttons[i] = new XOButton();
            p.add(buttons[i]);
        }
        add(p);
        setVisible(true);
    }
}



import javax.swing.JButton;
import javax.swing.ImageIcon;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;

public class XOButton extends JButton implements ActionListener{
    ImageIcon X,O;
    byte value=0;
	/*
	0:nothing
	1:X
	2:O
	*/

    public XOButton(){
        X=new ImageIcon(this.getClass().getResource("X.png"));
        O=new ImageIcon(this.getClass().getResource("O.png"));
        this.addActionListener(this);
    }

    public void actionPerformed(ActionEvent e){
        value++;
        value%=3;
        switch(value){
            case 0:
                setIcon(null);
                break;
            case 1:
                setIcon(X);
                break;
            case 2:
                setIcon(O);
                break;
        }
    }
}
