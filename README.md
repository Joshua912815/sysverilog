# sysverilog

```
module decoder (
    input  logic [3:0] sw,   // sw[3]=D, sw[2]=C, sw[1]=B, sw[0]=A
    output logic [6:0] seg   // seg[6:0] = a b c d e f g
);

    always_comb begin
        case (sw)
            4'h0: seg = 7'b1111110; // 0
            4'h1: seg = 7'b0110000; // 1
            4'h2: seg = 7'b1101101; // 2
            4'h3: seg = 7'b1111001; // 3
            4'h4: seg = 7'b0110011; // 4
            4'h5: seg = 7'b1011011; // 5
            4'h6: seg = 7'b1011111; // 6
            4'h7: seg = 7'b1110000; // 7
            4'h8: seg = 7'b1111111; // 8
            4'h9: seg = 7'b1110011; // 9
            4'hA: seg = 7'b1110111; // A
            4'hB: seg = 7'b0011111; // B
            4'hC: seg = 7'b1001110; // C
            4'hD: seg = 7'b0111101; // D
            4'hE: seg = 7'b1001111; // E
            4'hF: seg = 7'b1000111; // F
            default: seg = 7'b0000000;
        endcase
    end

endmodule
```




```
# sw input
set_property -dict {PACKAGE_PIN M21 IOSTANDARD LVCMOS33} [get_ports sw[3]];
set_property -dict {PACKAGE_PIN N20 IOSTANDARD LVCMOS33} [get_ports sw[2]];
set_property -dict {PACKAGE_PIN N22 IOSTANDARD LVCMOS33} [get_ports sw[1]];
set_property -dict {PACKAGE_PIN P21 IOSTANDARD LVCMOS33} [get_ports sw[0]];

# seg output
set_property -dict {PACKAGE_PIN Y21 IOSTANDARD LVCMOS33} [get_ports seg[6]];
set_property -dict {PACKAGE_PIN AB22 IOSTANDARD LVCMOS33} [get_ports seg[5]];
set_property -dict {PACKAGE_PIN AA18 IOSTANDARD LVCMOS33} [get_ports seg[4]];
set_property -dict {PACKAGE_PIN AB18 IOSTANDARD LVCMOS33} [get_ports seg[3]];
set_property -dict {PACKAGE_PIN AA20 IOSTANDARD LVCMOS33} [get_ports seg[2]];
set_property -dict {PACKAGE_PIN AB21 IOSTANDARD LVCMOS33} [get_ports seg[1]];
set_property -dict {PACKAGE_PIN AA21 IOSTANDARD LVCMOS33} [get_ports seg[0]];

set_property CFGBVS VCCO [current_design]
set_property CONFIG_VOLTAGE 3.3 [current_design]
```
