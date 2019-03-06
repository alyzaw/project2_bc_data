We wanted to collect reviews for various types of birth control, so that we may potentially analyze feedback provided by women and discover if there are trends that arise within the experiences women have with each birth control option currently on the market.

To collect this data, I used the websites [Everyday Health](https://www.everydayhealth.com/drugs/) and [Drugs.com](https://www.drugs.com/). These sites both host reviews for all sorts of prescription drugs and contained thousands of thorough reviews of all types of birth control. After some research, I learned that the primary birth control options currently available fall into eight categories: combination pill (estrogen and progestin), progestin only pill, hormonal intra-uterine device (IUD), non-hormonal (copper) IUD, vaginal ring, patch, implant, and shot. On the Everyday Health website drugs are rated by brand, so I found the brand or generic version of each type that had the most posted reviews and used those for my dataset. Unfortunately, this site did not host reviews for any types of non-hormonal IUDs. On drugs.com, the reviews were not as well organized, with some sorted by brand, some by type, and many duplicate sites. I chose the pages that seemed to be the most cohesive for each type of birth control I was looking for.

Using Splinter, I was able to scrape the review data for each type of birth control from the two sites. I parsed through the HTML coding to extract the review content, numeric rating, publish date, and (when available) I used the regular expression function to extract the reason for using birth control for each review instance. I added all of these variables to a pandas dataframe so I could clean and arrange the data as desired. I also ran all the reviews through VADER sentiment analysis so I could gather more objective datapoints from the subjective feedback collected, and added these to my dataframe as well.

Once I had extracted and organized the birth control data, I established connections with Amazon Web Services and MySQL so I could store my database both locally and remotely. One of the reviews caused errors in the transfer since it contained non-standard text (an emoji) so I dropped that row. Once I passed my dataset to AWS and MySQL using pandas to_sql function, I then read them back into my notebook to verify that the information populated correctly. 

Additionally, we compiled the reported side effects (by the pharmaceutical companies) for each drug from [RxList](https://www.rxlist.com) which we put into a datapbase and saved on AWS and MySQL as well.

Now that I have an amazing collection of data on this topic, I’m very excited to see what I can learn about birth control!

[Click here to see how we pulled data from Everyday Health](https://github.com/alyzaw/project2_bc_data/blob/master/Project_2_Birth_Control.ipynb)

[Click here to see how we pulled data from Drugs.com](https://github.com/alyzaw/project2_bc_data/blob/master/Project_2_Birth_Control_Site2.ipynb)

[Click here to see how we pulled data from RxList]
(https://github.com/alyzaw/project2_bc_data/blob/master/Project2_Side_Effects.ipynb)
