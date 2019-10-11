# Notify
[![](https://jitpack.io/v/qq524787275/Notify.svg)](https://jitpack.io/#qq524787275/Notify)

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
	
	dependencies {
	        implementation 'com.github.qq524787275:Notify:v1.0'
	}
	
	
    private fun createNotification() {
        val pendingIntent = NavDeepLinkBuilder(requireActivity())
            .setGraph(R.navigation.navigation_main)
            .setDestination(R.id.fragmentLanguages)
            .createPendingIntent()
        notifyManager.getCreator()
            .meta {
                clickIntent = pendingIntent
            }
            .content {
                title = "有一条新消息"
                text = "Deeplink跳转到切换语言界面"
            }
            .show(1)
    }
