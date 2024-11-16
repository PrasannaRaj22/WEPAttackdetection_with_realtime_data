# WEPAttackdetection_with_realtime_data
This tool detects Deauthentication and Disassociation attacks in 802.11 networks by analyzing a given .pcap file. It logs suspicious activity, such as repetitive attack patterns, and sends SMS alerts for critical events.
Features

    Packet Analysis: Processes management frames (deauth/disassoc) in .pcap files to identify potential attacks.
    Spam Detection: Tracks repeated suspicious packets using a spam analyzer.
    Alert System: Sends SMS alerts using the Twilio API when attack thresholds are exceeded.
    Attack Logs: Logs attack details, including MAC addresses, sequence numbers, and fragment numbers, into an output file.

How It Works

    Reads and processes a .pcap file provided as input.
    Filters for deauth and disassoc packets using a BPF filter.
    Analyzes packets for patterns of repeated attacks.
    Sends an SMS alert if a critical repetition threshold is crossed.

Requirements

    Dependencies:
        libpcap-dev
        curl for Twilio SMS integration
    Environment:
        GCC for compilation
        Internet access for SMS alert functionality
Usage
Compiling and Running

    Ensure libpcap is installed:

sudo apt-get install libpcap-dev

Compile and run the program using the provided bash script:

./script.sh <input_pcap_file> <output_log_file>

Example:

./script.sh SC_input.pcap error_log.txt
