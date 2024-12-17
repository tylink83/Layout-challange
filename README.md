//
//  strech 3.swift
//  Layout Challenge
//
//  Created by Link, Ty - Student on 8/29/24.
//

import SwiftUI

struct strech_3: View {
    var body: some View {
        VStack{
            ExtractedView3()
            
            HStack(spacing: 15) {
                PriceingView3(title: "Basic", price: "$9", textColor: .white, bgImage: "clouds")
                ZStack {
                    PriceingView3(title: "Pro", price: "$19", textColor: .white, bgImage: "scace2")
                    Text("Best for designer")
                        .font(.system(.caption, design: .rounded))
                        .fontWeight(.bold)
                        .foregroundStyle(.white)
                        .padding(5)
                        .background(Color(red: 255/255, green: 183/255, blue: 37/255))
                        .offset(x: 0, y: 87)
                }
                
            }
           
            .padding(11)
            ZStack {
                PriceingView3(title: "Team", price: "$299", textColor: .white, bgImage: "purrple", icon: "wand.and.rays")
                
                Text("Perfet for teams with 20 members")
                    .font(.system(.caption, design: .rounded))
                    .fontWeight(.bold)
                    .foregroundStyle(.white)
                    .padding(5)
                    .background(Color(red: 255/255, green: 183/255, blue: 37/255))
                    .offset(x:0, y: 110)
                
                    .padding(100)
            }
                Spacer()
            }
        .padding(.horizontal)
        }
    }


#Preview {
    strech_2()
}

struct ExtractedView3: View {
    
    var body: some View {
        HStack {
            VStack(alignment: .leading, spacing: 2) {
                Text("Choose")
                    .font(.system(.largeTitle, design: .rounded))
                    .fontWeight(.black)
                Text("Your Plan")
                    .font(.system(.largeTitle, design: .rounded))
                    .fontWeight(.black)
            }
            Spacer()
        }
        .padding()
    }
}

struct PriceingView3: View {
    
    var title: String
    var price: String
    var textColor: Color
    var bgImage: String
    var icon: String?
    
    var body: some View {
            VStack {
                
                if let icon = icon {
                    Image(systemName: icon)
                        .font(.largeTitle)
                        .foregroundStyle(textColor)
                }
                Text(title)
                    .font(.system(.title, design: .rounded))
                    .fontWeight(.black)
                    .foregroundStyle(textColor)
                Text(price)
                    .font(.system(size: 40, weight: .heavy, design: .rounded))
                    .foregroundStyle(textColor)
                Text("per month")
                    .font(.headline)
                    .foregroundStyle(textColor)
            }
            .frame(minWidth: 0, maxWidth: .infinity, minHeight: 100)
            .padding(40)
            .background(Image(bgImage))
            .cornerRadius(10)
            
        }
}

#Preview {
    strech_3()
}
