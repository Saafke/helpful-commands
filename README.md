# helpful-commands
All the commands I use reguluarly

#### Open and Save JSON
```
f = open('data.json')
data = json.load(f)


```

#### Imshow
```
cv2.imshow("window name", out-image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

#### Convert video to images
```
ffmpeg -i s1v1.avi %06d.png

# Vice versa
ffmpeg -i %04d.png output.mp4

# If the filenames don't begin with 0 or have missing indices
ffmpeg -framerate 5 -pattern_type glob -i '*.png' out.mp4
```

#### Clip video (order of arguments matter!)
```
ffmpeg -ss 0 -t 15 -i squats_feedback.mp4 -acodec copy -vcodec copy side_view.mp4
```

#### Crop video
```
# out_w is the width of the output rectangle
# out_h is the height of the output rectangle
# x and y specify the top left corner of the output rectangle
ffmpeg -i in.mp4 -filter:v "crop=out_w:out_h:x:y" out.mp4

```

#### Recode
```
ffmpeg -i %06d.png -c:v copy -pix_fmt yuv420p out.mp4
```

#### Leading zeros
```
"{:04d}.png".format(counter)
```

#### Scan size of /root
```
cd /
ncdu -x / 
```


#### Clean tmp
```
cd /tmp/
pwd
sudo rm -r *
```

#### Clean logs
```
sudo journalctl --vacuum-size=100M
```
