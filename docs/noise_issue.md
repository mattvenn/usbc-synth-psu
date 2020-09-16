# Noise issue

After plugging the Kaoss pad and volca together I heard a lot of bad noise.

Posted in 1bit squared [electronics discussion channel](https://discord.com/channels/613131135903596547/701517294697840700/755165090306719846) (registration required but info copied here).

Connections and results shown in this image:

![connections](noisy_connections.jpg)

Noise recording is [here](noise.wav)

User Obliterous on the discord thought it would be a ground loop related issue and suggested making a common mode choke with a decoupling capacitor on each side.

I made a test board:

![common mode choke](common_mode_choke.jpg)

And tested it with a 10k -> 10M sweep. Green is input and yellow is output. The filter removes all the signal above about 100khz.

![choke test](choke_test.PNG)

I will test this in between the Kaoss pad and the PSU.

# Wed 16 Sep 10:38:31 CEST 2020

Tried yesterday but now the PSU can't even power the kaoss pad. See the main project log for notes on this.
Did try with the POs and they have the same problem that I couldn't resolve with the choke or the audio filter.
