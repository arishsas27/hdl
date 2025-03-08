module full_adder(a,b,cin,sum,carry);
input a,b,cin;
output sum,carry;
assign sum=a^b^cin;
assign  carry=(a&b)|(b&cin)|(a&cin);
endmodule

module ripple_4bit(a,b,cin,sum,carry);
input [3:0]a,b;
input cin;
output [3:0]sum;
output carry;
wire c0,c1,c2;
full_adder dut1(a[0],b[0],cin,sum[0],c0);
full_adder dut2(a[1],b[1],c0,sum[1],c1);
full_adder dut3(a[2],b[2],c1,sum[2],c2);
full_adder dut4(a[3],b[3],c2,sum[3],c3);
endmodule
