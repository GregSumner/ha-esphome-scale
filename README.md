# Home Assistant ESPHome Smart Scale
STLs and ESPHome config for a scale intended to sit in front of my cat's food bowl to track her struggles to lose weight.

![alt text](https://github.com/GregSumner/ha-esphome-scale/assets/4370367/615ba12f-f403-499a-8fef-8704f8d469ab)![alt text](https://github.com/GregSumner/ha-esphome-scale/assets/4370367/d5b47529-a8ce-494b-b1b4-44e3d2ebc74e)![alt text](https://github.com/GregSumner/ha-esphome-scale/assets/4370367/35d48c10-0486-4afc-9462-76ca81e623f7)

(220mm x 220mm x 40mm)


I printed this with supports in the load cell holes, it resulted in quite a lot of support-unpicking in front of the TV, but I can't print bridges reliably. The load cell holes were designed at 12.9mm. Off of my printer my calipers said the result was 12.6mm and that resulted in a tight push fit that practically didn't need screws. If your printer under-prints by any more you'll struggle to insert the load cells. This was designed for an eBay load cell that was 12.5mm x 12.5mm x 80mm, but I didn't order additional ones carefully from Aliexpress and they were 70mm long and M4 tapped on both sides (rather than M5 on one side) - I've used the 70mm ones without adjusting the design and only using one screw hole and it's all turned out alright.

![alt text](https://github.com/GregSumner/ha-esphome-scale/assets/4370367/eb75df70-1d79-4f25-8429-c189da4b7865)![alt text](https://github.com/GregSumner/ha-esphome-scale/assets/4370367/a4f51391-5c95-4e56-98fc-384c135454bf)

Care is needed when inserting the load cells into the base, there is a cut-out in the print but you'll need to neatly fold the wires down in a 'U' shape to come back out of the load cell hole. The print unfortunately shaves some of the silicone but it hasn't caused me a problem yet. The photo has the wiring drilled through as the printed-in tunnel was too small, I've since enlarged the tunnel which should fix the problem.


![alt text](https://github.com/GregSumner/ha-esphome-scale/assets/4370367/03c2bf22-7d04-47bb-ae94-b4012cfcabac)

I put a coat of plasti-dip on the bottom thinking it would make a nice non-slip surface, maybe it would work if I put more coats but one coat was thinner than I expected and had too many peaks and valleys to give good grip on wood floor. I ended up with double sided tape which has worked well.


![alt text](https://github.com/GregSumner/ha-esphome-scale/assets/4370367/d4370dd4-8288-4264-9978-f0e76dc25ffb)

The wiring can be almost anything you want, this is what I did.

I calibrated each of the load cells after installing/wiring in the base, but before installing the platform. I weighed a bottle on a kitchen scale and then, after uploading the ESPHome firmware with the "calibrate_linear" filters removed, watched the logs and noted the 'zero' count and 'bottle' count. Those should then be substituted into "calibrate_linear".

The output in Home Assistant should be stream of readings at 2Hz while the cat is on the scale. I would like to eventually emulate a human scale and present one number from a weigh-in, I think it would involve sampling until the variance settles and then averaging the low varience data... but for now it's raw values. A manual tare button in Home Assistant zeros both of the load cells, I've only had to zero it a couple of times and it's only ever drifted by a couple of grams anyway.

On the cat behaviour front - I had to initially put sides up to stop her walking around the scale. With it not sliding or rocking she now uses it happily. I also had to 'encourage' her back paws on initially, if I had a larger printer I think I'd make the platform 10% bigger but she took the hint and now sits fully on the scale.
