*** Taches ***
* gpsUtil : trop lent : obtenir 100 000 emplacements d'utilisateurs - de 15 minutes.
* RewardsCentral : trop lent : obtenir des récompenses pour 100 000 utilisateurs  - de 20 minutes.
* tripPricer : doit fonctionner avec les préférences de voyage de l'utilisateur.
* bug des destinations recommandées aux utilisateurs : Ajouter les 5 attractions les plus proches par rapport au dernier emplacement de l'utilisateur peu importe leur distance.
* bugs des tests unitaires :  échouent par intermittence.
* Aligner les tests unitaires de performances existants avec les corrections pour prouver l'amélioration de la rapidité.

libs >
gpsUtil.jar
RewardCentral.jar
TripPricer.jar

src >
Application
TourGuideController
TourGuideModule
    getGpsUtil
    getRewardsService
        GpsUtil + RewardCentral
    getRewardCentral

tracker >
    Tracker
        ExecutorService
        TourGuideService

service >
    RewardsService
    TourGuideService
        gpsUtil
        RewardService
        TripePricer
        Tracker

        initializeInternalUsers

user >
User // model
UserPreferences // user settings
UserRewards // Reward
    VisitedLocation
    Attraction
    Points