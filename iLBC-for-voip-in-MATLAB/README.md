## iLBC
This example implements the Internet Low Bitrate Codec (iLBC) and illustrates its use. iLBC is designed for encoding and decoding
speech for transmission via V oIP (V oice Over Internet Protocol).

## VoIP
Voice over Internet Protocol is the family of technologies that allows IP networks to be used for voice applications such as telephony
and teleconferencing. Compression is normally required to reduce the bandwidth requirements of these applications. For efficiency ,
VoIP is often implemented using the lightweight but unreliable User Datagram Protocol (UDP). Packet loss correction is needed to
maintain received voice quality over lossy networks.

## Basic iLBC Design and Performance
iLBC is designed for compression of speech to be transmitted over the Internet.  Thus, its algorithms are only meant to cover the narrow frequency range of 90-4000
Hz and it implements perceptual coding tuned to normal speech. All input signals to the iLBC encoder must be Pulse Code Modulated (PCM) speech signals
sampled at exactly 8000 Hz with 16-bit samples ranging from -32768 to +32767.
iLBC is defined for two different transmission rates, with a packet of data being encoded either after every 30ms or after every 20ms of speech. The advantage of
encoding every 30ms is that the encoded data rate is lower: 13.33 kbit/sec as opposed to 15.20 kbit/sec for 20ms frames. However, encoding every 30ms leads to
50% more delay in the received speech, which can cause undesirable latency .
Since all inputs to iLBC must be 8000 Hz, 16-bit PCM speech, the input rate is (8000 Hz) * (16 bits) = 128 kbit/sec. Thus, iLBC compresses the speech to 10.4% and
1 1.9% of the original data-rate for 13.33 kbit/sec and 15.20 kbit/sec modes, respectively.
