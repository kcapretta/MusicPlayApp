//
//  ButtonScreen.swift
//  MusicPlay
//
//  Created by Kassandra Capretta on 10/18/19.
//  Copyright © 2019 Kassandra Capretta. All rights reserved.
//

import UIKit
import MediaPlayer

var musicPlayer = MPMusicPlayerController.applicationMusicPlayer // or ()?

class ButtonScreen: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()

      
    }
    @IBAction func buttonTapped(_ sender: UIButton) {
        
        MPMediaLibrary.requestAuthorization { (status) in
            if status == .authorized {
                self.playGenre(genre: sender.currentTitle!)
            }
        }
    }
    @IBAction func stopButtonTapped(_ sender: UIButton) {
        musicPlayer.stop()
    }
    
    @IBAction func nextButtonTapped(_ sender: UIButton) {
        musicPlayer.skipToNextItem()
    }
    
    func playGenre(genre: String) {
        musicPlayer.stop()
        
        let query = MPMediaQuery()
        let predicate = MPMediaPropertyPredicate(value: genre, forProperty: MPMediaItemPropertyGenre)
        
        query.addFilterPredicate(predicate)
        
        musicPlayer.setQueue(with: query)
        musicPlayer.shuffleMode = .songs
        musicPlayer.play()
    }
}
