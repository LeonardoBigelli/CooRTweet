# CooRTweet 2.1.0

- Added a new multi-modal and multi-platform dataset for testing and demonstration purposes (see documentation for "german_elections" data).
- Updated the vignette
- New function to simulate data

# CooRTweet 2.0.2

Edit the function documentation to address specific issues and enhance clarity. This includes removing obsolete information about min_repetition in the detect_groups documentation and correcting typos in the vignettes.

# CooRTweet 2.0.1

Fixed a bug that under certain circumstances prevented the number of shares from being calculated correctly with the accounts_stats function.

# CooRTweet 2.0.0

A major release with many important breaking changes. Package users upgrading to version 2.0.0
should pay attention to the functions `detect_groups` and `generate_coordinated_network`

## New features

- completely reworked the code that generates the coordination network. There is now a
    new function `generate_coordinated_network`
- The results from `detect_groups` can now be subset into "faster" subnetworks with the new function `flag_speed_share`
- The `prep_data` function helps to bring other social media data into the right shape

## Changes

Most changes are related to two areas of improvement: the way how the coordination network is 
generated and naming conventions used in this package

- `detect_coordinated_groups` function was renamed to `detect_groups`, alognside we also renamed
    the `min_repetition` to `min_participation` to better reflect its meaning. 
    The function generally performs still performs the same operation as before.
- `generate_network` was removed and replaced with `generate_coordination_network`, 
    which is a completely rewritten approach to the network generation.
- We globally changed the wording of "user" to "account", which is more faithful to 
    the theoretical framework of this package. The term "account" describes the data much better.
- Therefore, the column formally named `id_user` (found in many functions) was 
    now renamed to `account_id`

## Dropped Features

We decided to drop the feature to detect cotweeting behaviour based on text similarity for this
release. In practical applications, the `detect_similar_text` function was not performing up
to our standards and we are currently looking into a fresh approach to implement such a feature.

# CooRTweet 1.4.0

This is a minor release adding new features

## New features

* Added `detect_similar_text()` function that finds tweets based on text similarity (cotweets). Refer to the documentation for details.
* The `reshape_tweets()` function was extended with the `intent = "cotweet"`, which reformats your data to fit in the `detect_similar_text()` function
