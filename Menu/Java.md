---
---
# Java

자바 GUI를 사용하여 TicTacToe 게임을 구현해 보았습니다. 

화면 구성은 3가지로 구상하여 첫 번째 화면에서 O를 할지 X를 할지, Single로 할지 Together로 할지 선택하며 선택한 버튼에 따라 두 번째 화면과 세 번째 화면으로 넘어갑니다. 두 번째 화면은 Single 패널로 AI 와 Player가 게임하도록 하였고, 세 번째 화면은 Together 패널로 친구와 번걸아가며 게임을 할 수 있도록 구상하였습니다. 레이아웃을 넘어가기위해 CardLayout을 사용 하였으며 Flag를 설정하여 O, X, Single, Together 버튼의 경우의 수에 따라 레이아웃 전환이 가능하도록 구현하였습니다.Ai 알고리즘은 Minimax 알고리즘을 사용하였으며 메뉴바에는 개발정보, 게임규칙, 새로운 게임, 게임 종료 등을 넣었습니다.

---
## Game Screen
![Java_1](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Java_1.png)

---
## Screen Composition Diagram
![Java_2](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Java_2.png)

---
## TicTacToe
### Source Code

    import java.awt.BorderLayout;
    import java.awt.CardLayout;
    import java.awt.Color;
    import java.awt.Component;
    import java.awt.Container;
    import java.awt.Font;
    import java.awt.Frame;
    import java.awt.GridLayout;
    import java.awt.event.ActionEvent;
    import java.awt.event.ActionListener;
    import java.awt.event.MouseEvent;
    import java.awt.event.MouseListener;

    import javax.swing.AbstractButton;
    import javax.swing.JButton;
    import javax.swing.JDialog;
    import javax.swing.JFrame;
    import javax.swing.JLabel;
    import javax.swing.JMenu;
    import javax.swing.JMenuBar;
    import javax.swing.JMenuItem;
    import javax.swing.JOptionPane;
    import javax.swing.JPanel;
    import javax.swing.SwingConstants;
    import javax.swing.SwingUtilities;

    public class TicTacToe extends JFrame implements ActionListener {

      /*
       * Cyber Security Programming 
       * Professor, Ki-hyun, Jeong
       * Made By TaeYeong, Jeong
       * Since `20.6.16.~30. Tic-Tac-Toe
       */

      // 크기 지정
      public static final int WIDTH = 331;
      public static final int HEIGHT = 450;
      // 하고싶은 버튼, 플레이어 스타일의 플래그 설정
      int BOF, BXF, BSF, BTF;

      // CardLayout으로 레이아웃 관리
      private CardLayout cards = new CardLayout();

      // 메뉴 바
      private JMenuBar menuBar;
      // Game, Option, Help 메뉴바
      private JMenu Emag, Snoitpo, Pleh;
      // 메뉴 아이템들
      private JMenuItem Ofni, Niam, Tser, Tixe, Pleh2;
      // Inof, help 다이어그램
      JDialog OfniDialog, Pleh2Dialog;

      JLabel OfniDialogLabel, Pleh2DialogLabel;

      public TicTacToe() {
        // 기본 설정
        // Swing Case 1 프라임 제목 설정
        this.setTitle("Tic Tae Toe");
        // Swing Case 1 프라임 사이즈 설정
        this.setSize(WIDTH, HEIGHT);
        // Swing Case 1 프라임 X 버튼 클릭시 닫힘
        this.setDefaultCloseOperation(EXIT_ON_CLOSE);
        // 레이아웃 변경을 위해 getContent 사용
        this.getContentPane().setLayout(cards);

        getContentPane().add("One", new BasicPanel(this));
        // ======================================
        // Menu Bar 구성==========================
        menuBar = new JMenuBar();

        // Menu Bar Option
        // 1. Game
        Emag = new JMenu("Game");
        // Infomation
        Ofni = new JMenuItem("Infomation");
        Emag.add(Ofni);
        Ofni.addActionListener(this);

        // 2. Options
        Snoitpo = new JMenu("Options");
        // 메인 화면 구현
        Niam = new JMenuItem("Main");
        Snoitpo.add(Niam);
        Niam.addActionListener(this);
        // 새게임 구현
        Tser = new JMenuItem("New Game");
        Snoitpo.add(Tser);
        Tser.addActionListener(this);
        // 게임 종료버튼 구현
        Tixe = new JMenuItem("Exit");
        Snoitpo.add(Tixe);
        Tixe.addActionListener(this);

        // 3. Help
        Pleh = new JMenu("Help");
        // Tic Tac toe Manual
        Pleh2 = new JMenuItem("Help");
        Pleh.add(Pleh2);
        Pleh2.addActionListener(this);

        menuBar.add(Emag);
        menuBar.add(Snoitpo);
        menuBar.add(Pleh);

        setJMenuBar(menuBar);
        // ======================================

        this.setVisible(true);
      }

      // 첫 번째 패널로 넘김
      public void changeOnePanel(int BOF, int BXF, int BSF, int BTF) {
        this.BOF = BOF;
        this.BXF = BXF;
        this.BSF = BSF;
        this.BTF = BTF;
        cards.show(getContentPane(), "One");
      }

      // 두 번째 패널로 넘김
      public void changeTwoPanel(int BOF, int BXF, int BSF, int BTF) {
        this.BOF = BOF;
        this.BXF = BXF;
        this.BSF = BSF;
        this.BTF = BTF;
        // 두 번째 패널 생성
        getContentPane().add("Two", new SingleGamePanel(this, BOF, BXF));
        cards.show(getContentPane(), "Two");
      }

      // 세 번째 패널로 넘김
      public void changeThreePanel(int BOF, int BXF, int BSF, int BTF) {
        this.BOF = BOF;
        this.BXF = BXF;
        this.BSF = BSF;
        this.BTF = BTF;
        // 세 번째 패널 생성
        getContentPane().add("Three", new TogetGamePanel(this, BOF, BXF));
        cards.show(getContentPane(), "Three");
      }

      public CardLayout getCardLayout() {
        return cards;
      }

      @Override
      public void actionPerformed(ActionEvent e) {
        // TODO Auto-generated method stub
        if (e.getSource() == Ofni) {
          // JDialog를 이용한 정보 상자
          OfniDialog = new JDialog(this, "Infomation", true);
          OfniDialog.setLocation(0, 0);
          OfniDialog.setSize(WIDTH, HEIGHT);
          OfniDialogLabel = new JLabel("<html><body>"
              + "**Cyber Security Programming**<br>"
              + "**Professor, Ki-hyun, Jeong**<br>"
              + "**Made By TaeYeong, Jeong**<br>"
              + "**Since `20.6.16.~30.**<br>"
              + "**Tic-Tac-Toe**<br>"
              + "**version: 1.0.2**<br>"
              + "</body></html>");
          OfniDialogLabel.setFont(new Font("굴림", Font.PLAIN, 18));
          OfniDialog.add(OfniDialogLabel);
          OfniDialog.setVisible(true);
        }
        if (e.getSource() == Niam) {
          changeOnePanel(BOF, BXF, BSF, BTF);
        }
        if (e.getSource() == Tser) {
          // 새 게임 등록
          // System.out.println(BOF + ". " + BXF + ", " + BSF + ", " + BTF);
          changeOnePanel(BOF, BXF, BSF, BTF);
          // 싱글 모드
          if ((BOF == 1 && BSF == 1) || (BXF == 1 && BSF == 1)) {
            changeTwoPanel(BOF, BXF, BSF, BTF);
          }

          // 투게더 모드
          if ((BOF == 1 && BTF == 1) || (BXF == 1 && BTF == 1) || BTF == 1) {
            changeThreePanel(BOF, BXF, BSF, BTF);
          }
        }
        if (e.getSource() == Tixe) {
          System.exit(0);
        }
        if (e.getSource() == Pleh2) {
          // JDialog를 이용한 메뉴얼 상자
          Pleh2Dialog = new JDialog(this, "Manual", true);
          Pleh2Dialog.setLocation(0, 0);
          Pleh2Dialog.setSize(WIDTH, HEIGHT);
          Pleh2DialogLabel = new JLabel("<html><body>"
              + "Korean<br>"
              + "Manual<br>"
              + "1. O, X 중 1Player가 하고싶은 버튼을 클릭 합니다.<br>"
              + "2. 혼자서 할지(AI와 함께), 둘이서(친구와 함께) 할지 선택합니다.<br>"
              + "3. 게임이 시작됩니다. <br><br>"
              + "Rule<br>"
              + "1) 9칸 위에 1P는 O(or X), 2P는 X(or O)를 번갈아가며 버튼을 클릭합니다.<br>"
              + "2) 먼저 O나 X를 3개가 직선으로 이어지게 만들면 승리합니다.<br><br><br>"
              + "-English<br>"
              + "1. Click the button you want to use between O and X.<br>"
              + "2. Choose whether to do it alone (with AI) or two (with friends).<br>"
              + "3. The game starts.<br><br>"
              + "Rule<br>"
              + "1) Click the button on the 9 spaces, alternating between O(or X) for 1P and X(or O) for 2P.<br>"
              + "2) First you win by making three O or X straight.<br>"
              + "</body></html>");
          Pleh2DialogLabel.setFont(new Font("굴림", Font.PLAIN, 13));
          Pleh2Dialog.add(Pleh2DialogLabel);
          Pleh2Dialog.setVisible(true);
        }
      }

      public static void main(String[] args) {
        // 그래픽 전용 thread 사용하기
        SwingUtilities.invokeLater(new Thread() {
          public void run() {
            new TicTacToe();
          }
        });
      }
    }

    class BasicPanel extends JPanel implements ActionListener, MouseListener {
      // OX 버튼 크기
      public static final int OX = 90;
      // 뼈대 프라임
      private Frame F;
      // 하고싶은 O, X, 플레이 스타일 
      private JButton buttonO, buttonX, buttonSingle, buttonToget;
      // 하고싶은 버튼, 플레이어 스타일의 플래그 설정
      private int BOF = 0, BXF = 0, BSF = 0, BTF = 0;

      // 첫번 째 패널 
      public BasicPanel(Frame f) {
        setSize(WIDTH, HEIGHT);
        setLayout(null);
        setBackground(Color.WHITE);
        F = f;

        // 기본화면 버튼 구현=========================
        buttonO = new JButton("O");
        buttonX = new JButton("X");
        // 버튼 위치, 크기 지정
        buttonO.setBounds(50, 100, OX, OX);
        buttonX.setBounds(175, 100, OX, OX);
        // 버튼 폰트 지정
        buttonO.setFont(new Font("impact", Font.PLAIN, 90));
        buttonX.setFont(new Font("impact", Font.PLAIN, 90));

        buttonSingle = new JButton("Single");
        buttonToget = new JButton("Together");
        // 버튼 위치, 크기 지정
        buttonSingle.setBounds(108, 230, 100, 25);
        buttonToget.setBounds(108, 280, 100, 25);

        // 버튼 MouseListener등록
        buttonO.addMouseListener(this);
        buttonX.addMouseListener(this);
        buttonSingle.addMouseListener(this);
        buttonToget.addMouseListener(this);

        // OX버튼 중복 검사 MouseListener()
        MouseListener OX;
        buttonO.addMouseListener(OX = new MouseListener() {

          @Override
          public void mouseClicked(MouseEvent e) {
            // TODO Auto-generated method stub
          }

          @Override
          public void mousePressed(MouseEvent e) {
            // TODO Auto-generated method stub
            // 버튼 중복 검사
            // 둘 중 한곳만 선택 하기
            if ((BOF == 1 && BXF == 0) || (BOF == 0 && BXF == 1)) {
              BOF = 0;
              BXF = 0;
              buttonO.setBackground(Color.WHITE);
              buttonX.setBackground(Color.WHITE);
            }
          }

          @Override
          public void mouseReleased(MouseEvent e) {
            // TODO Auto-generated method stub
          }

          @Override
          public void mouseEntered(MouseEvent e) {
            // TODO Auto-generated method stub
          }

          @Override
          public void mouseExited(MouseEvent e) {
            // TODO Auto-generated method stub
          }

        });
        buttonX.addMouseListener(OX);

        // Single, Together 버튼 중복 검사 MouseListener()
        MouseListener ST;
        buttonSingle.addMouseListener(ST = new MouseListener() {

          @Override
          public void mouseClicked(MouseEvent e) {
            // TODO Auto-generated method stub
          }

          @Override
          public void mousePressed(MouseEvent e) {
            // TODO Auto-generated method stub
            // 버튼 중복 검사
            // 둘 중 한곳만 선택하기
            if ((BSF == 1 && BTF == 0) || (BSF == 0 && BTF == 1)) {
              BSF = 0;
              BTF = 0;
              buttonSingle.setBackground(Color.WHITE);
              buttonToget.setBackground(Color.WHITE);
            }
          }

          @Override
          public void mouseReleased(MouseEvent e) {
            // TODO Auto-generated method stub
          }

          @Override
          public void mouseEntered(MouseEvent e) {
            // TODO Auto-generated method stub
          }

          @Override
          public void mouseExited(MouseEvent e) {
            // TODO Auto-generated method stub
          }

        });
        buttonToget.addMouseListener(ST);

        // 배경색 지정
        buttonO.setBackground(Color.WHITE);
        buttonX.setBackground(Color.WHITE);
        buttonSingle.setBackground(Color.WHITE);
        buttonToget.setBackground(Color.WHITE);

        add(buttonSingle);
        add(buttonToget);
        add(buttonO);
        add(buttonX);
        // ======================================
        this.setVisible(true);
      }

      public void actionPerformed(ActionEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseClicked(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mousePressed(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseReleased(MouseEvent e) {
        // TODO Auto-generated method stub
        // Button O Flag 검사
        if (e.getSource() == buttonO && BOF == 0) {
          buttonO.setBackground(Color.red);
          BOF = 1;
        } else if (e.getSource() == buttonO && BOF == 1) {
          buttonO.setBackground(Color.WHITE);
          BOF = 0;
        }

        // Button X Flag 검사
        if (e.getSource() == buttonX && BXF == 0) {
          buttonX.setBackground(Color.red);
          BXF = 1;
        } else if (e.getSource() == buttonX && BXF == 1) {
          buttonX.setBackground(Color.WHITE);
          BXF = 0;
        }

        // Button Single Flag 검사
        if (e.getSource() == buttonSingle && BSF == 0) {
          buttonSingle.setBackground(Color.red);
          BSF = 1;
        } else if (e.getSource() == buttonSingle && BSF == 1) {
          buttonSingle.setBackground(Color.WHITE);
          BSF = 0;
        }

        // 버튼 Together Flag 검사
        if (e.getSource() == buttonToget && BTF == 0) {
          buttonToget.setBackground(Color.red);
          BTF = 1;
        } else if (e.getSource() == buttonToget && BTF == 1) {
          buttonToget.setBackground(Color.WHITE);
          BTF = 0;
        }

        // 싱글 모드
        if ((BOF == 1 && BSF == 1) || (BXF == 1 && BSF == 1)) {
          // 싱글 모드는 두 번째 패널로 이동 
          ((TicTacToe) F).changeTwoPanel(BOF, BXF, BSF, BTF);
        }

        // 투게더 모드
        if ((BOF == 1 && BTF == 1) || (BXF == 1 && BTF == 1) || BTF == 1) {
          // O, X를 선택하지 않으면 기본적으로 선이 O를 선택
          if (BOF == 0 && BXF == 0) {
            BOF = 1;
          }
          // 투게더 모드는 세 번째 패널로 이동
          ((TicTacToe) F).changeThreePanel(BOF, BXF, BSF, BTF);
        }
      }

      @Override
      public void mouseEntered(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseExited(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      int getBOF() {
        return BOF;
      }

      int getBXF() {
        return BXF;
      }
    }

    class SingleGamePanel extends JPanel implements ActionListener, MouseListener {
      // 스코어 값
      private int sco1 = 0;
      // 스코어 값
      private int sco2 = 0;

      Frame F;

      // 버튼 붙일 패널
      private JPanel nineButtons;
      // 게임 스코어 붙일 레이블, 현재 차례
      private JLabel outcome, currentPlayer;

      // 빈 버튼
      JButton tempButton;

      // 게임의 끝을 알리는 변수
      boolean isGameEnd = false;
      // 시작 플레이어 1
      private final int START_PLAYER = 1;

      // 게임 실행
      TicTacToeCore ttt = new TicTacToeCore(START_PLAYER);

      public SingleGamePanel(Frame f, int BOF, int BXF) {
        ttt.first(BOF, BXF);
        // 기본화면 설정
        F = f;
        setSize(WIDTH, HEIGHT);
        setBackground(Color.WHITE);
        setLayout(new BorderLayout());
        // ================================================
        // 1. 상단 바 구성(승, 패)==============================
        outcome = new JLabel(sco1 + " : " + sco2);
        outcome.setHorizontalAlignment(SwingConstants.CENTER);
        add(outcome, BorderLayout.NORTH);
        // ================================================
        // 2. 버튼 구성
        // 버튼 9개를 붙일 패널을 GridLayout로 지정한다.
        nineButtons = new JPanel();
        nineButtons.setLayout(new GridLayout(3, 3));
        // 빈 버튼 9개를 생성 후 nineButtons Panel에 붙인다.
        for (int i = 0; i < 9; i++) {
          tempButton = new JButton("");
          // 버튼 폰트, 색 지정
          tempButton.setFont(new Font("impact", Font.PLAIN, 90));
          tempButton.setBackground(Color.WHITE);
          nineButtons.add(tempButton);
        }
        add(nineButtons, BorderLayout.CENTER);
        // 버튼마다 마우스 이벤트 등록
        for (Component c : nineButtons.getComponents()) {
          c.addMouseListener(this);
        }
        // ================================================
        // 3. 하단 바 구성(current turn)=======================
        currentPlayer = new JLabel(" ");
        currentPlayer.setHorizontalAlignment(SwingConstants.CENTER);
        add(currentPlayer, BorderLayout.SOUTH);
        // ================================================
        f.setVisible(true);
      }

      public class TicTacToeCore {
        // 현재 플레이어 상태를 나타내는 변수
        private int currentPlayerNum;
        // 게임오버를 나타내는 변수
        private boolean isGameOver = false;
        // 게임끝 났을 때 게임판
        private int[][] endStage;
        // O, X선을 결정하는 변수
        String First, Secend;
        // 현재 플레이어의 값을 넘겨받는 함수
        public TicTacToeCore(int currentPlayerNum) {
          this.currentPlayerNum = currentPlayerNum;
        }

        // MiniMax 알고리즘을 사용한 AI 인공지능
        public int Ai(int[][] ticArr, int a) {
          // 게임이 끝났는지 검사를 함
          int winner = ttt.inputCurrentStage(ticArr);
          for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
              //ticArr[i][j] = 0;
              System.out.print(ticArr[i][j]);
            }
            System.out.println();
          }
          System.out.println();
          // winner의 값이 1 또는 2일 경우 게임의 승리(Player1 or Player2)로 게임이 끝남
          if(winner == 1 || winner == 2) return winner;

          // winner의 값이 -99 또는 99일 경우 무승부로 게임이 끝남
          if(winner == -99 || winner == 99) return 0;

          // move1, 2의 초기 값 설정
          int move1 = -1;
          int move2 = -1;
          //경우의 수의 최솟값 설정
          int score = 100;

          for (int i = 0; i < ticArr.length; i++) {
            for (int j = 0; j < ticArr[0].length; j++) {
              if (ticArr[i][j] == 0 ){
                ticArr[i][j] = a;

                int thisScore = -Ai(ticArr, a = (a == 1) ? 2 : 1);
                if(thisScore == -1 || thisScore == -2) {
                  a = (a == 1) ? 2 : 1;
                }
                if(thisScore == 1 || thisScore == 2) {
                  a = (a == 1) ? 2 : 1;
                }
                ticArr[i][j] = 0;
                //thisScore의 최댓값 찾기
                if(thisScore > score) {
                  score = thisScore;
                  //최대값일 때의 좌표를 찾음
                  move1 = i;
                  move2 = j;
                }
              }
            }
          }
          if(move1 == -1 && move2 == -1)
            return 0;
          return score;
        }

        // 차례로 번갈아가며 턴을 넘김
        public void changeTurn() {
          currentPlayerNum = (currentPlayerNum == 1) ? 2 : 1;
        }

        // 먼저 선(O버튼이 선일지 B버튼이 선일지) 결정
        public void first(int BOF, int BXF) {
          // BOF = 1;
          if (BOF == 1) {
            First = "O";
            Secend = "X";
          }
          // BOX = 1;
          if (BXF == 1) {
            First = "X";
            Secend = "O";
          }
        }

        // O, X버튼 순서 접근자
        String getFirst() {
          return First;
        }

        // O, X버튼 순서 접근자
        String getSecend() {
          return Secend;
        }

        // 플레이어 상태 접근자
        public int getCurrentPlayerNum() {
          return currentPlayerNum;
        }

        // 플레이어 상태 생성자
        public void setCurrentPlayerNum(int currentPlayerNum) {
          this.currentPlayerNum = currentPlayerNum;
        }

        // 게임 끝
        public int[][] getEndStage() {
          return endStage;
        }

        /*
         * @return -99: 게임종료됨, 1: 플레이어 1 승리, 2: 플레이어 2 승리, 0: 진행중, 99: 비김(draw)
         */
        // 게임을 진행
        public int inputCurrentStage(int[][] currentStage) {
          // 게임이 끝났다면 더 이상 진행하는 의미가 없으므로 판단 중단
          if (isGameOver) {
            return -99;
          }
          int currentTurn = 1;
          for (int i = 0; i < currentStage.length; i++) {
            String rowStr = "";
            String colStr = "";
            String diagStr1 = "";
            String diagStr2 = "";
            // 가로, 세로를 이어 붙임
            for (int j = 0; j < currentStage[i].length; j++) {
              rowStr += (currentStage[i][j] + "");
              colStr += (currentStage[j][i] + "");
            }
            // 대각선을 이어 붙임
            for (int j = 0; j < currentStage.length; j++) {
              diagStr1 += currentStage[j][j];
              diagStr2 += currentStage[j][2 - j];
            }

            // 플레이어 2 승리 조건
            if (isThisPlayerWin(2, rowStr, colStr, diagStr1, diagStr2)) {
              return 2;
              // 플레이어 1 승리 조건
            } else if (isThisPlayerWin(1, rowStr, colStr, diagStr1, diagStr2)) {
              return 1;
              // 게임 턴이 9턴이 지나면 무승부
            } else if (currentTurn == 9) {
              return 99;
            } else {
              continue;
            }
          }
          currentTurn++;
          return 0;
        }

        // 게임 승리를 판단하는 함수
        private boolean isThisPlayerWin(int playerNum, String rowFrag, String colFrag, String diagFrag1,
            String diagFrag2) {
          String p = String.valueOf(playerNum);
          boolean result = false;
          String[] arr = { rowFrag, colFrag, diagFrag1, diagFrag2 };
          // 가로, 세로, 대각선 중 같은 문자가 3개일 경우를 검사하는 함수
          for (int i = 0; i < arr.length; i++) {
            result = !arr[i].contains("X") && arr[i].equals(p + p + p);
            if (result) {
              return result;
            }
          }
          return result;
        }

        // 게임 리셋시킴
        public void resetGame(int currentPlayerNum) {
          this.isGameOver = false;
          this.currentPlayerNum = currentPlayerNum;
          this.endStage = null;
        }
      }

      public void actionPerformed(ActionEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseClicked(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mousePressed(MouseEvent e) {
        // TODO Auto-generated method stub
        JButton tempButton = (JButton) e.getComponent();
        // 게임이 끝났는지 검사하는 함수
        if (isGameEnd) {
          return;
        }
        // 이미 둔 자리에 두면 경고를 출력하는 함수
        if (tempButton.getText().equals("O") || tempButton.getText().equals("X")) {
          JOptionPane.showMessageDialog(nineButtons, "이미 둔 곳입니다.");
          return;
          // 하단바에 현재 플레이어 차례를 나타내는 함수
        } else if (ttt.getCurrentPlayerNum() == 1) {
          tempButton.setText(ttt.getFirst());
          currentPlayer.setText("Player " + 2 + "turn");
          System.out.println();
          // 턴을 넘김
        }// else {

        int[][] ticArr2 = new int[3][3];
        // 문자 O, X에 따라 값 1, 2를 지정
        for (int i = 0; i < ticArr2.length; i++) {
          for (int j = 0; j < ticArr2[0].length; j++) {
            String pl = ((JButton) nineButtons.getComponent(j + i * 3)).getText();
            // 문자가 O이면 값 1 지정
            if (pl.equals(ttt.getFirst()))
              ticArr2[i][j] = 1;
            // 문자가 X이면 값 2를 지정
            else if (pl.equals(ttt.getSecend()))
              ticArr2[i][j] = 2;
            // 공백은 값 0 지정
            else
              ticArr2[i][j] = 0;
          }
        }

        int result = ttt.inputCurrentStage(ticArr2);

        // 결과가 승, 패 라면
        if (result == 1 || result == 2) {
          JOptionPane.showMessageDialog(nineButtons, "플레이어 " + result + "의 승리입니다.");
          if (result == 1) {
            // 1스코어 증가
            sco1++;
          } else {
            // 2스코어 증가
            sco2++;
          }
          // 스코어 갱신
          outcome.setText(sco1 + " : " + sco2);
          // 게임 끝
          isGameEnd = true;
          // 게임 리셋
          ttt.resetGame(START_PLAYER);
          // 게임 변수 초기화
          isGameEnd = false;
          // 버튼을 값 초기화
          for (int i = 0; i < nineButtons.getComponents().length; i++) {
            ((JButton) nineButtons.getComponent(i)).setText("");
          }
          // 비겼을 때
        } else if (result == 99) {
          JOptionPane.showMessageDialog(nineButtons, "비겼습니다.");
          // 게임 끝
          isGameEnd = true;
          // 게임 리셋
          ttt.resetGame(START_PLAYER);
          // 게임 변수 초기화
          isGameEnd = false;
          // 버튼을 값 초기화
          for (int i = 0; i < nineButtons.getComponents().length; i++) {
            ((JButton) nineButtons.getComponent(i)).setText("");
          }
        }
      }

      @Override
      public void mouseReleased(MouseEvent e) {
        // TODO Auto-generated method stub
        int[][] ticArr = new int[3][3];
        // 문자 O, X에 따라 값 1, 2를 지정
        for (int i = 0; i < ticArr.length; i++) {
          for (int j = 0; j < ticArr[0].length; j++) {
            String pl = ((JButton) nineButtons.getComponent(j + i * 3)).getText();
            // 문자가 O이면 값 1 지정
            if (pl.equals(ttt.getFirst()))
              ticArr[i][j] = 1;
            // 문자가 X이면 값 2를 지정
            else if (pl.equals(ttt.getSecend()))
              ticArr[i][j] = 2;
            // 공백은 값 0 지정
            else
              ticArr[i][j] = 0;
          }
        }

          int move1 = 1;
          int move2 = 1;
          int score = 100;
          int a = 2;
          int[][] ticArrM = new int[3][3];

          for (int i = 0; i < ticArr.length; i++) {
            //System.out.println("tl: " + ticArr.length);
            for (int j = 0; j < ticArr[0].length; j++) {
              //System.out.println("tl[0]: " + ticArr[0].length);
              if(ticArr[i][j] == 1) {
                ticArrM[i][j] = 1;
              } else if(ticArr[i][j] == 2) {
                ticArrM[i][j] = 2;
              } else if(ticArr[i][j] == 0) {
                ticArrM[i][j] = a;
                int tempScore = -ttt.Ai(ticArrM, a = (a == 1) ? 2 : 1);
                if(tempScore == -1 || tempScore == -2) {
                  a = (a == 1) ? 2 : 1;
                }
                if(tempScore == 1 || tempScore == 2) {
                  a = (a == 1) ? 2 : 1;
                }
                ticArrM[i][j] = 0;
                if (tempScore < score) {
                  score = tempScore;
                  move1 = i;
                  move2 = j;
                }
              }
            }
          }
          int k = (move1 * 3) + move2;
          //ticArrM[move1][move2] = a;
          ((JButton) nineButtons.getComponent(k)).setText(ttt.getSecend());
          currentPlayer.setText("Player " + 1 + "turn");

        int[][] ticArr2 = new int[3][3];
        // 문자 O, X에 따라 값 1, 2를 지정
        for (int i = 0; i < ticArr2.length; i++) {
          for (int j = 0; j < ticArr2[0].length; j++) {
            String pl = ((JButton) nineButtons.getComponent(j + i * 3)).getText();
            // 문자가 O이면 값 1 지정
            if (pl.equals(ttt.getFirst()))
              ticArr2[i][j] = 1;
            // 문자가 X이면 값 2를 지정
            else if (pl.equals(ttt.getSecend()))
              ticArr2[i][j] = 2;
            // 공백은 값 0 지정
            else
              ticArr2[i][j] = 0;
          }
        } 

        int result = ttt.inputCurrentStage(ticArr2);
        int result2 = score;
        System.out.println(result + " " + result2);
        // 결과가 승, 패 라면
        if (result == 1 || result == 2) {
          JOptionPane.showMessageDialog(nineButtons, "플레이어 " + result + "의 승리입니다.");
          if (result == 1) {
            // 1스코어 증가
            sco1++;
          } else {
            // 2스코어 증가
            sco2++;
          }
          // 스코어 갱신
          outcome.setText(sco1 + " : " + sco2);
          // 게임 끝
          isGameEnd = true;
          // 게임 리셋
          ttt.resetGame(START_PLAYER);
          // 게임 변수 초기화
          isGameEnd = false;
          // 버튼을 값 초기화
          for (int i = 0; i < nineButtons.getComponents().length; i++) {
            ((JButton) nineButtons.getComponent(i)).setText("");
          }
          // 비겼을 때
        } else if (result == 99) {
          JOptionPane.showMessageDialog(nineButtons, "비겼습니다.");
          // 게임 끝
          isGameEnd = true;
          // 게임 리셋
          ttt.resetGame(START_PLAYER);
          // 게임 변수 초기화
          isGameEnd = false;
          // 버튼을 값 초기화
          for (int i = 0; i < nineButtons.getComponents().length; i++) {
            ((JButton) nineButtons.getComponent(i)).setText("");
          }
        }
      }
      @Override
      public void mouseEntered(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseExited(MouseEvent e) {
        // TODO Auto-generated method stub
      }
    }

    class TogetGamePanel extends JPanel implements ActionListener, MouseListener {
      // 스코어 값
      private int sco1 = 0;
      // 스코어 값
      private int sco2 = 0;

      // 뼈대 프라임
      private Frame F;

      // 버튼 붙일 패널
      private JPanel nineButtons;
      // 게임 스코어 붙일 레이블, 현재 차례
      private JLabel outcome, currentPlayer;

      // 게임의 끝을 알리는 변수
      boolean isGameEnd = false;
      // 시작 플레이어 1
      private final int START_PLAYER = 1;

      // 게임 실행
      TicTacToeCore ttt = new TicTacToeCore(START_PLAYER);

      public TogetGamePanel(Frame f, int BOF, int BXF) {
          ttt.first(BOF, BXF);
          // 기본화면 설정
          setSize(WIDTH, HEIGHT);
          setBackground(Color.WHITE);
          setLayout(new BorderLayout());
          F = f;
          // ================================================
          // 1. 상단 바 구성(승, 패)==============================
          outcome = new JLabel(sco1 + " : " + sco2);
          outcome.setHorizontalAlignment(SwingConstants.CENTER);
          add(outcome, BorderLayout.NORTH);
          // ================================================
          // 2. 버튼 구성
          // 버튼 9개를 붙일 패널을 GridLayout로 지정한다.
          nineButtons = new JPanel();
          nineButtons.setLayout(new GridLayout(3, 3));
          // 빈 버튼 9개를 생성 후 nineButtons Panel에 붙인다.
          for (int i = 0; i < 9; i++) {
            JButton tempButton = new JButton("");
            // 버튼 폰트, 색 지정
            tempButton.setFont(new Font("impact", Font.PLAIN, 90));
            tempButton.setBackground(Color.WHITE);
            nineButtons.add(tempButton);
          }
          add(nineButtons, BorderLayout.CENTER);
          // 버튼마다 마우스 이벤트 등록
          for (Component c : nineButtons.getComponents()) {
            c.addMouseListener(this);
          }
          // ================================================
          // 3. 하단 바 구성(current turn)=======================
          currentPlayer = new JLabel(" ");
          currentPlayer.setHorizontalAlignment(SwingConstants.CENTER);
          add(currentPlayer, BorderLayout.SOUTH);
          // ================================================
          f.setVisible(true);
        }

      public class TicTacToeCore {
        // 현재 플레이어 상태를 나타내는 변수
        private int currentPlayerNum;
        // 게임오버를 나타내는 변수
        private boolean isGameOver = false;
        // 게임끝 났을 때 게임판
        private int[][] endStage;
        // 게임을 진행하는 차레 수
        private int currentTurn = 1;
        // 선을 결정하는 변수
        String First, Secend;

        public TicTacToeCore(int currentPlayerNum) {
          this.currentPlayerNum = currentPlayerNum;
        }

        // 차례로 번갈아가며 턴을 넘김
        public void changeTurn() {
          currentPlayerNum = (currentPlayerNum == 1) ? 2 : 1;
        }

        // 먼저 선(O버튼이 선일지 B버튼이 선일지) 결정
        public void first(int BOF, int BXF) {
          // BOF = 1;
          if (BOF == 1) {
            First = "O";
            Secend = "X";
          }
          // BOX = 1;
          if (BXF == 1) {
            First = "X";
            Secend = "O";
          }
        }

        // O, X버튼 순서 접근자
        String getFirst() {
          return First;
        }

        // O, X버튼 순서 접근자
        String getSecend() {
          return Secend;
        }

        // 플레이어 상태 접근자
        public int getCurrentPlayerNum() {
          return currentPlayerNum;
        }

        // 플레이어 상태 생성자
        public void setCurrentPlayerNum(int currentPlayerNum) {
          this.currentPlayerNum = currentPlayerNum;
        }

        // 게임 끝
        public int[][] getEndStage() {
          return endStage;
        }

        /*
         * @return -99: 게임종료됨, 1: 플레이어 1 승리, 2: 플레이어 2 승리, 0: 진행중, 99: 비김(draw)
         */
        // 게임을 진행
        public int inputCurrentStage(int[][] currentStage) {
          // 게임이 끝났다면 더 이상 진행하는 의미가 없으므로 판단 중단
          if (isGameOver) {
            return -99;
          }

          for (int i = 0; i < currentStage.length; i++) {
            String rowStr = "";
            String colStr = "";
            String diagStr1 = "";
            String diagStr2 = "";
            // 가로, 세로를 이어 붙임
            for (int j = 0; j < currentStage[i].length; j++) {
              rowStr += (currentStage[i][j] + "");
              colStr += (currentStage[j][i] + "");
            }
            // 대각선을 이어 붙임
            for (int j = 0; j < currentStage.length; j++) {
              diagStr1 += currentStage[j][j];
              diagStr2 += currentStage[j][2 - j];
            }

            // 플레이어 2 승리 조건
            if (isThisPlayerWin(2, rowStr, colStr, diagStr1, diagStr2)) {
              isGameOver = true;
              endStage = currentStage;
              return 2;
              // 플레이어 1 승리 조건
            } else if (isThisPlayerWin(1, rowStr, colStr, diagStr1, diagStr2)) {
              isGameOver = true;
              endStage = currentStage;
              return 1;
              // 게임 턴이 9턴이 지나면 무승부
            } else if (currentTurn == 9) {
              return 99;
            } else {
              continue;
            }
          }
          currentTurn++;
          return 0;
        }

        // 게임 승리를 판단하는 함수
        private boolean isThisPlayerWin(int playerNum, String rowFrag, String colFrag, String diagFrag1,
            String diagFrag2) {
          String p = String.valueOf(playerNum);
          boolean result = false;
          String[] arr = { rowFrag, colFrag, diagFrag1, diagFrag2 };
          // 가로, 세로, 대각선 중 같은 문자가 3개일 경우를 검사하는 함수
          for (int i = 0; i < arr.length; i++) {
            result = !arr[i].contains("0") && arr[i].equals(p + p + p);
            //System.out.println("rF" + rowFrag + ", cF" + colFrag + ", dF1" + diagFrag1 + ", dF2" + diagFrag2);
            if (result) {
              //System.out.println(result + " 1");
              return result;
            }
          }
          //System.out.println(result + " 2");
          return result;
        }

        // 게임 리셋시킴
        public void resetGame(int currentPlayerNum) {
          this.isGameOver = false;
          this.currentPlayerNum = currentPlayerNum;
          this.endStage = null;
          this.currentTurn = 1;
        }
      }

      public void actionPerformed(ActionEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseClicked(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mousePressed(MouseEvent e) {
        // TODO Auto-generated method stub
        JButton tempButton = (JButton) e.getComponent();
        // 게임이 끝났는지 검사하는 함수
        if (isGameEnd) {
          return;
        }
        // 이미 둔 자리에 두면 경고를 출력하는 함수
        if (tempButton.getText().equals("O") || tempButton.getText().equals("X")) {
          JOptionPane.showMessageDialog(nineButtons, "이미 둔 곳입니다.");
          return;
          // 하단바에 현재 플레이어 차례를 나타내는 함수
        } else if (ttt.getCurrentPlayerNum() == 1) {
          tempButton.setText(ttt.getFirst());
          currentPlayer.setText("Player " + 2 + "turn");
          //System.out.println();
          // 하단바에 현재 플레이어 차례를 나타내는 함수
        } else {
          tempButton.setText(ttt.getSecend());
          currentPlayer.setText("Player " + 1 + "turn");
        }

        // 턴을 넘김
        ttt.changeTurn();

        // 좌표값 출력
        //System.out.print("(" + e.getX() + ", " + e.getY() + ") ");

        // 게임 판
        int[][] ticArr = new int[3][3];
        // 문자 O, X에 따라 값 1, 2를 지정
        for (int i = 0; i < ticArr.length; i++) {
          for (int j = 0; j < ticArr[0].length; j++) {
            String pl = ((JButton) nineButtons.getComponent(j + i * 3)).getText();
            //System.out.println(pl);
            // 문자가 O이면 값 1 지정
            if (pl.equals(ttt.getFirst()))
              ticArr[i][j] = 1;
            // 문자가 X이면 값 2를 지정
            else if (pl.equals(ttt.getSecend()))
              ticArr[i][j] = 2;
            // 공백은 값 0 지정
            else
              ticArr[i][j] = 0;
          }
        }
        int result = ttt.inputCurrentStage(ticArr);
        // System.out.println(result);
        // System.out.println("result: " + result);

        // 결과가 플레이어의 승리라면
        if (result == 1 || result == 2) {
          JOptionPane.showMessageDialog(nineButtons, "플레이어 " + result + "의 승리입니다.");
          if (result == 1) {
            // 1스코어 증가
            sco1++;
          } else {
            // 2스코어 증가
            sco2++;
          }
          // 스코어 갱신
          outcome.setText(sco1 + " : " + sco2);
          // 게임 끝
          isGameEnd = true;
          // 게임 리셋
          ttt.resetGame(START_PLAYER);
          // 게임 변수 초기화
          isGameEnd = false;
          // 버튼을 값 초기화
          for (int i = 0; i < nineButtons.getComponents().length; i++) {
            ((JButton) nineButtons.getComponent(i)).setText("");
          }
          // 비겼을 때
        } else if (result == 99) {
          JOptionPane.showMessageDialog(nineButtons, "비겼습니다.");
          // 게임 끝
          isGameEnd = true;
          // 게임 리셋
          ttt.resetGame(START_PLAYER);
          // 게임 변수 초기화
          isGameEnd = false;
          // 버튼을 값 초기화
          for (int i = 0; i < nineButtons.getComponents().length; i++) {
            ((JButton) nineButtons.getComponent(i)).setText("");
          }
        }
      }

      @Override
      public void mouseReleased(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseEntered(MouseEvent e) {
        // TODO Auto-generated method stub
      }

      @Override
      public void mouseExited(MouseEvent e) {
        // TODO Auto-generated method stub
      }

    }

---
## 설명
### Minimax 
Single Play에서 컴퓨터의 알고리즘은 Minimax 알고리즘을 사용 했는데 Minimax 알고리즘은 최악의 경우 발생가능한 손실(최대손실)을 최소화 한다는 규칙입니다. 원래 두 명의 참가자가 존재하는 제로섬 게임 이론으로부터 시작하였으나 (두 참가자가 순차적으로 행동하는 경우와 동시에 행동하는 경우 모두 포함), 더 복잡한 게임과 불확실성이 존재할 때의 일반적인 의사결정에 이르기까지 널리 쓰이고 있습니다.

### 개발 후기
개발 할 때 생각보다 많은 어려움이 있었는데 처음에는 버튼을 클릭 시 원하는 레이아웃을 어떻게 불러올지 난감했습니다. 오랜시간 고민 끝에 인 터넷을 통해 CardLayout을 사용하여 원하는 레이아웃을 불러올 수 있다는 것을 알게 되어 CardLayout을 사용하여 패널을 구성하였습니다. 또 다른 어려움에는 게임을 진행하는 이벤트처리 외에도 MiniMax 알고리즘을 구현하는데 상당히 많은 시간을 사용했습니다. 먼저 알고리즘을 이해하는데 10시간 정도 시간이 걸렸는데 막상 구현할려고 하니 정말 막막했습니다. 60~70시간 정도 걸려 마침내 알고리즘 구현은 완벽하게 했지만 값을 넘겨받는 과정에서 오류가 발생해 오류발생 원인을 찾아보니 파라미터 인자값이 제대로 넘어가지 않는 문제있었습니다. 하지만 이 문제를 해결하기 위해선 지금 구현한 알고리즘을 처음부터 다시 다른 방법으로 짜야 하는데 어디서 부터 시작할지 몰라 최대한 할 수 있는데까지 구현하였습니다. 개발을 하면서 정말 힘들었지만 유익하고 재밌는 시간이었습니다.
