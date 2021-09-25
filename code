import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

/**
 * This is a GUI Calculator.
 *
 * @author Harindi Thanthiriwaththage
 * @version V1.0 (26.09.2021)
 */
public class Cal5001 extends JFrame implements ActionListener {
    //Holds calculator display
    JTextField display; 
    //Holds all calculator buttons
    JButton[] buttons;
    //Array holding button labels
    String[] buttonNames = {"1","2","3","4","5","6","7","8","9","+/-","0",".",
        "=","+","<<","-","C","*","(","/",")","!","OFF"};
    //Array holding button commands
    String[] buttonCommands = {"CMD_1","CMD_2","CMD_3","CMD_4","CMD_5","CMD_6",
        "CMD_7","CMD_8","CMD_9","CMD_+/-","CMD_0","CMD_DOT","CMD_EQL","CMD_ADD",
        "CMD_BSP","CMD_SUB","CMD_CLR","CMD_MUL","CMD_(","CMD_DIV","CMD_)",
        "CMD_FAC","CMD_OFF"};
        
    /**
     * Constructor for objects of class Cal5001
     */
    public Cal5001(){
        // initialise instance variables
        super("My PROG5001 - Calculator");
        setSize(450, 380);
        CreateCalcGUI();
    }

    /**
     * Initialize calculator GUI.
    */
    private void CreateCalcGUI() {
        //panel top text field area
        JPanel panelTop = new JPanel();
        panelTop.setBackground(Color.white);
        GridLayout panelTopLayout = new GridLayout(0,1);
        panelTop.setLayout(panelTopLayout); 
        
        // rightside calculator layout
        JPanel panelLeftButtons = new JPanel();
        panelLeftButtons.setBackground(Color.white);
        GridBagLayout panelLeftButtonsLayout = new GridBagLayout();
        panelLeftButtons.setLayout(panelLeftButtonsLayout);
        
        //leftside calculator layout
        JPanel panelRightButtons = new JPanel();
        panelRightButtons.setBackground(Color.white);
        GridBagLayout panelRightButtonsLayout = new GridBagLayout();
        panelRightButtons.setLayout(panelRightButtonsLayout);
        
        //main panel with all the buttons
        JPanel panelCenter = new JPanel();
        panelCenter.setBackground(Color.white);
        GridBagLayout panelCenterLayout = new GridBagLayout();
        panelCenter.setLayout(panelCenterLayout);
        
        //Grid constraints for panelCenter
        GridBagConstraints panelC = new GridBagConstraints();
        panelC.fill = GridBagConstraints.BOTH;
        panelC.gridwidth = 2;
        panelC.weightx = 1.0;
        
        //Place left buttons and right buttons on panelCenter
        panelCenterLayout.setConstraints(panelLeftButtons, panelC);
        panelCenter.add(panelLeftButtons);
        panelCenterLayout.setConstraints(panelRightButtons, panelC);
        panelCenter.add(panelRightButtons);
        
        //calculator text field
        display = new JTextField("");     
        Font displayFont = new Font("SansSerif", Font.BOLD, 24);
        display.setFont(displayFont);
        display.setBackground(Color.white);   
        display.setHorizontalAlignment(JTextField.RIGHT);        
        display.setPreferredSize(new Dimension(100,35));
        display.setEnabled(false);
        panelTop.add(display);
    
        //Main layout of the calculator
        BorderLayout mainLayout = new BorderLayout();
        setLayout(mainLayout);
        add(panelTop, BorderLayout.NORTH);
        add(panelCenter, BorderLayout.CENTER);
        
        //Store calculator buttons
        buttons = new JButton[23];
        
        //Constraints for panelLeftButtons
        GridBagConstraints panelLeftButtonsC = new GridBagConstraints();
        panelLeftButtonsC.fill = GridBagConstraints.BOTH;
        panelLeftButtonsC.insets = new Insets(5,5,5,5);
        
        //Populate buttons on the left panel
        for(int i=0; i<13; i++) {
            //Find column index
            int column = i%3;
            
            if(i == 12) {
                //If last index (equals sign) fill remaining space
                panelLeftButtonsC.gridwidth = GridBagConstraints.REMAINDER;
                panelLeftButtonsC.weightx = 3.0;
            } else
            if(column == 2) {
                //If last column move to new line
                panelLeftButtonsC.gridwidth = GridBagConstraints.REMAINDER;
                panelLeftButtonsC.weightx = 1.0;
            } else {
                //If not last column set 3 grids horizontally
                panelLeftButtonsC.gridwidth = 3;
                panelLeftButtonsC.weightx = 1.0;
            }

            //Create buttons from buttonNames and buttonCommands
            buttons[i] = new JButton();
            buttons[i].setPreferredSize(new Dimension(50,50));
            buttons[i].setText(buttonNames[i]);
            buttons[i].setActionCommand(buttonCommands[i]);
            buttons[i].addActionListener(this);
            buttons[i].setBackground(Color.gray);
            panelLeftButtonsLayout.setConstraints(buttons[i], panelLeftButtonsC);
            panelLeftButtons.add(buttons[i]);
        }
        
        //Constraint for panelRightButtons
        GridBagConstraints panelRightButtonsC = new GridBagConstraints();
        panelRightButtonsC.fill = GridBagConstraints.BOTH;
        panelRightButtonsC.insets = new Insets(5,5,5,5);
        
        //Populate buttons on the right panel
        for(int i=13; i<23; i++) {
            //Find column index
            int column = i%2;
            
            if(column == 0) {
                //If last column items should be 2 times bigger
                panelRightButtonsC.gridwidth = GridBagConstraints.REMAINDER;
                panelRightButtonsC.weightx = 2.0;
            } else {
                //If not last column items should be normal size
                panelRightButtonsC.gridwidth = 2;
                panelRightButtonsC.weightx = 1.0;
            }
            
            //Create buttons from buttonNames and buttonCommands
            buttons[i] = new JButton();
            buttons[i].setPreferredSize(new Dimension(50,50));
            buttons[i].setText(buttonNames[i]);
            buttons[i].setActionCommand(buttonCommands[i]);
            buttons[i].addActionListener(this);
            buttons[i].setBackground(Color.gray);
            panelRightButtonsLayout.setConstraints(buttons[i], panelRightButtonsC);
            panelRightButtons.add(buttons[i]);
        }
    }
    
    /**
     * Implementing ActionEvent interface to perform button clicks
     * @param: ActionEvent - handle button clicks 
     * @output: Display the input nymber or function 
     */
    public void actionPerformed(ActionEvent e) {
        String displayText;
        displayText = display.getText();
        String command = e.getActionCommand();
        if (command.equals("CMD_1")) {
            displayText = displayText + "1";
        } else
        if (command.equals("CMD_2")) {
            displayText = displayText + "2";
        } else
        if (command.equals("CMD_3")) {
            displayText = displayText + "3";
        } else
        if (command.equals("CMD_4")) {
            displayText = displayText + "4";
        } else
        if (command.equals("CMD_5")) {
            displayText = displayText + "5";
        } else
        if (command.equals("CMD_6")) {
            displayText = displayText + "6";
        } else
        if (command.equals("CMD_7")) {
            displayText = displayText + "7";
        } else
        if (command.equals("CMD_8")) {
            displayText = displayText + "8";
        } else
        if (command.equals("CMD_9")) {
            displayText = displayText + "9";
        } else
        if (command.equals("CMD_0")) {
            displayText = displayText + "0";
        } else
        if (command.equals("CMD_DOT")) {
            displayText = displayText + ".";
        } else
        
        // clear display
        if (command.equals("CMD_CLR")) {
            displayText = "";
        } else
        
        // Backspace
        if (command.equals("CMD_BSP")) {
            int len = displayText.length();
            displayText = displayText.substring(0, len-1);
        } else 
        
        // assining minus values
        if(command.equals("CMD_+/-")){
            int len = displayText.length();
            if(len > 0) {
                char lastChar = displayText.charAt(len-1);
                if(lastChar == '-') {
                    displayText = displayText.substring(0, len-1);
                } else {
                    displayText = displayText + "-";
                }
            } else {
                displayText = displayText + "-";
            }
        } else 
        
        //assining operators 
        if(command.equals("CMD_ADD")){
            displayText = displayText + "+";
        } else 
        if(command.equals("CMD_SUB")){
            displayText = displayText + "-";
        } else 
        if(command.equals("CMD_MUL")){
            displayText = displayText + "*";
        } else 
        if(command.equals("CMD_DIV")){
            displayText = displayText + "/";
        } else 
        if(command.equals("CMD_FAC")){
            displayText = displayText + "!";
        } else 
        if(command.equals("CMD_(")){
            displayText = displayText + "(";
        } else 
        if(command.equals("CMD_)")){
            displayText = displayText + ")";
        } else 
        if(command.equals("CMD_OFF")){
            System.exit(0);
        } else 
        if(command.equals("CMD_EQL")){
            displayText = CalculateExpression(displayText);
        }
        display.setText(displayText);
    }
    
    /**
     * Calculates and returns the answer to the given expression
     * @param: expression - the mathematical expression to be calculates
     * @output: returns the answer as a String for the given expression
     */
    private String CalculateExpression(String expression) {
        double answer = 0.0;
        char[] expressionChars = expression.toCharArray();
        String newExpression = "";
        
        String currentOperand1 = "";
        String currentOperand2 = "";
        char currentOperator = ' ';
        char openParanthesis = ' ';
        
        String subExpression = "";
        
        //Evaluate expressions inside parentheses
        for(int i=0; i<expressionChars.length; i++) {
            if(isNumber(expressionChars[i])) {
                if(openParanthesis == '(') {
                    //If open parentheses found add number to subExpression 
                    //to be evaluated
                    subExpression += expressionChars[i];
                } else {
                    //If no paretheses found add number to newExpression to be
                    //evaluated
                    newExpression += expressionChars[i];
                }
            } else {
                if(expressionChars[i] == '(') {
                    //Record if open paretheses found
                    openParanthesis = expressionChars[i];
                } else
                if(expressionChars[i] == ')') {
                    //If close parenthese found evaluate subExpression and 
                    //add result to newExpression
                    char[] subExpressionChars = subExpression.toCharArray();
                    newExpression += BasicCalculation(subExpressionChars);
                    openParanthesis = ' ';
                    subExpression = "";
                } else {
                    if(openParanthesis == '(') {
                        //If parentheses found add operator to subExpression
                        subExpression += expressionChars[i];
                    } else {
                        //If parentheses not found add operator to 
                        //subExpression
                        newExpression += expressionChars[i];
                    }
                }
            }
        }
        
        expressionChars = newExpression.toCharArray();
        newExpression = "";
        
        //Factorial operator calculation
        for(int i=0; i<expressionChars.length; i++) {
            if(isNumber(expressionChars[i])) {
                //If number found hold to be used if factorial sign found.
                currentOperand1 = currentOperand1 + expressionChars[i];
            } else {
                if(expressionChars[i] == '!') {
                    //If factorial sign found find factorial for last number 
                    //found
                    int factorial = Factorial(currentOperand1);
                    newExpression += factorial;
                    currentOperand1 = "";
                } else {
                    //If no factorial sign found add operator directly to 
                    //newExpression
                    newExpression += currentOperand1;
                    newExpression += expressionChars[i];
                    currentOperand1 = "";
                }
            }
        }
        
        //If operand was not added previously add it to newExpressions
        if(!currentOperand1.equals("")) {
            newExpression += currentOperand1;
            currentOperand1 = "";
        }
        expressionChars = newExpression.toCharArray();
        //Evaluated basic expressions
        answer = BasicCalculation(expressionChars);
        return answer + "";
    }
    
    /**
     * Calculates and returns the answer to basic expressions
     * @param: expression - the mathematical expression to be calculated
     * @output: returns the answer as a String for the given expression
     */
    private double BasicCalculation(char[] expressionChars) {
        double answer = 0.0;
        String currentOperand1 = "";
        String currentOperand2 = "";
        char currentOperator = ' ';
        //Find operands and operator pairs to evaluate
        for(int i=0; i<expressionChars.length; i++) {
            if(isNumber(expressionChars[i])) {
                if(currentOperator == ' ') {
                    currentOperand1 = currentOperand1 + expressionChars[i];
                } else {
                    currentOperand2 = currentOperand2 + expressionChars[i];
                }
            } else {
                if(currentOperator == ' ') {
                    currentOperator = expressionChars[i];
                } else {
                    //If operand and operator are found do calculation
                    answer = CalculatorWithOperator(currentOperand1, currentOperand2, currentOperator);
                    currentOperand1 = answer + "";
                    currentOperand2 = "";
                    currentOperator = expressionChars[i];
                }
            }
        }
        
        //Do final calculation if previously not done
        if(!currentOperand1.equals("") && !currentOperand2.equals("") && currentOperator != ' ') {
            answer = CalculatorWithOperator(currentOperand1, currentOperand2, currentOperator);
        } else if(!currentOperand1.equals("")) {
            answer = Double.parseDouble(currentOperand1);
        }
        return answer;
    }
    
    /**
     * Basic calculation function check such as, +,-,*,/
     * @param: op1 - operand 1, op2 - operand 2, operator - operator to do calculation
     * @output: Calculate nubers if the functions are +,-,*,/
     */
     private double CalculatorWithOperator(String op1, String op2, char operator) {
        double op1Double = Double.parseDouble(op1);
        double op2Double = Double.parseDouble(op2);
        switch(operator) {
            case '+':
                return op1Double + op2Double; //addtion method
            case '-':
                return op1Double - op2Double; //subtracation method
            case '*':
                return op1Double * op2Double; //multiplication method 
            case '/':
                return op1Double / op2Double; // division method
        }
        return 0;
    }
    
    /**
     * Method to calculate the factorial
     * @param: value - value to calculate factorial for
     * @output: returns factorial for given number
     */
    private int Factorial(String value) {
        int number = Integer.parseInt(value);
        int factorial = 1;
        for(int i=1; i<=number; i++) {
            factorial = factorial * i;
        }
        return factorial;
    }
    
    /**
     * Check if given char is a number or a floating point
     * @param: value - value to check
     * @output: returns true if number or 'dot'. false if not.
     */
    private boolean isNumber(char value) {
        if(value == '.') {
            return true;
        }
        
        try {
            Double.parseDouble(value + "");
            return true;
        } catch(Exception e) {
            return false;
        }
    }
    
    /**
     * The main method
     */
    public static void main (String[] args) {
        Cal5001 calc = new Cal5001();
        calc.setVisible(true);
    }
}
