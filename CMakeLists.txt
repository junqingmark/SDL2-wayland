#author: MaJunqing
#date:   2016-05-07
#mail:   junqingmark@163.com

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(SDL2Test)

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/include)

SET(SRCS
	src/SDL.c
	src/SDL_assert.c
	src/SDL_error.c
	src/SDL_hints.c
	src/SDL_log.c

	src/atomic/SDL_atomic.c
	src/atomic/SDL_spinlock.c

	src/audio/SDL_audio.c
	src/audio/SDL_audiocvt.c
	src/audio/SDL_audiodev.c
	src/audio/SDL_audiotypecvt.c
	src/audio/SDL_mixer.c
	src/audio/SDL_wave.c
	src/audio/pulseaudio/SDL_pulseaudio.c
	src/audio/alsa/SDL_alsa_audio.c

	src/core/linux/SDL_dbus.c
	src/core/linux/SDL_evdev.c
	#src/core/linux/SDL_ibus.c
	src/core/linux/SDL_udev.c

	src/cpuinfo/SDL_cpuinfo.c

	#src/dynapi/SDL_dynapi.c

	src/events/SDL_clipboardevents.c
	src/events/SDL_dropevents.c
	src/events/SDL_events.c
	src/events/SDL_gesture.c
	src/events/SDL_keyboard.c
	src/events/SDL_mouse.c
	src/events/SDL_quit.c
	src/events/SDL_touch.c
	src/events/SDL_windowevents.c

	src/file/SDL_rwops.c

	src/filesystem/unix/SDL_sysfilesystem.c

	src/haptic/SDL_haptic.c
	src/haptic/linux/SDL_syshaptic.c

	src/joystick/SDL_gamecontroller.c
	src/joystick/SDL_joystick.c
	src/joystick/linux/SDL_sysjoystick.c

	src/loadso/dlopen/SDL_sysloadso.c

	src/power/linux/SDL_syspower.c

	src/render/SDL_render.c
	src/render/SDL_yuv_mmx.c
	src/render/SDL_yuv_sw.c
	src/render/opengles2/SDL_render_gles2.c
	src/render/opengles2/SDL_shaders_gles2.c
	src/render/software/SDL_blendfillrect.c
	src/render/software/SDL_blendline.c
	src/render/software/SDL_blendpoint.c
	src/render/software/SDL_drawline.c
	src/render/software/SDL_drawpoint.c
	src/render/software/SDL_render_sw.c
	src/render/software/SDL_rotate.c

	src/stdlib/SDL_getenv.c
	src/stdlib/SDL_iconv.c
	src/stdlib/SDL_malloc.c
	src/stdlib/SDL_qsort.c
	src/stdlib/SDL_stdlib.c
	src/stdlib/SDL_string.c

	src/thread/SDL_thread.c
	src/thread/pthread/SDL_syscond.c
	src/thread/pthread/SDL_sysmutex.c
	src/thread/pthread/SDL_syssem.c
	src/thread/pthread/SDL_systhread.c
	src/thread/pthread/SDL_systls.c

	src/timer/SDL_timer.c
	src/timer/unix/SDL_systimer.c

	src/video/SDL_blit.c
	src/video/SDL_blit_0.c
	src/video/SDL_blit_1.c
	src/video/SDL_blit_A.c
	src/video/SDL_blit_auto.c
	src/video/SDL_blit_copy.c
	src/video/SDL_blit_N.c
	src/video/SDL_blit_slow.c
	src/video/SDL_bmp.c
	src/video/SDL_clipboard.c
	src/video/SDL_egl.c
	src/video/SDL_fillrect.c
	src/video/SDL_pixels.c
	src/video/SDL_rect.c
	src/video/SDL_RLEaccel.c
	src/video/SDL_shape.c
	src/video/SDL_stretch.c
	src/video/SDL_surface.c
	src/video/SDL_video.c

	src/video/wayland/SDL_waylanddyn.c
	src/video/wayland/SDL_waylandevents.c
	src/video/wayland/SDL_waylandmouse.c
	src/video/wayland/SDL_waylandopengles.c
	src/video/wayland/SDL_waylandtouch.c
	src/video/wayland/SDL_waylandvideo.c
	src/video/wayland/SDL_waylandwindow.c


)

SET(SRCS1

	sdl_bmp.c


)

ADD_EXECUTABLE(${PROJECT_NAME} ${SRCS} ${SRCS1})
#ADD_LIBRARY(${PROJECT_NAME} SHARED ${SRCS})
TARGET_LINK_LIBRARIES(${PROJECT_NAME} EGL GLESv2 pulse png12 jpeg wayland-egl wayland-cursor wayland-client xkbcommon pthread m z dl pthread)
