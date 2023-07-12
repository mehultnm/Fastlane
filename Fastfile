# This file contains the fastlane.tools configuration
# You can find the documentation at https://docs.fastlane.tools
#
# For a list of all available actions, check out
#
#     https://docs.fastlane.tools/actions
#
# For a list of all available plugins, check out
#
#     https://docs.fastlane.tools/plugins/available-plugins
#

# Uncomment the line if you want fastlane to automatically update itself
# update_fastlane
fastlane_require 'screengrab'


default_platform(:android)

platform :android do
  desc "Runs all the tests"
  lane :generate_apk do
    gradle(task: "assemble",build_type:'Release')

  end




    desc "My awesome app"
    lane :distribute do
        gradle(
          task: "assemble",
          build_type: "Release"
        )
        release = firebase_app_distribution(
            app: "1:264961661102:android:70869fe971830f064d753f",
            testers: "mehultandeltnm@gmail.com,tandelmehul97@gmail.com",
            release_notes: "Lots of amazing new features to test out!"
        )
  end
    desc "Release for the Android beta"
    lane :beta do
      gradle(task: ‘clean’, project_dir: ‘android/gradle’)
      gradle(task: 'assemble', build_type: 'Release', project_dir: './android/')
    end
end
