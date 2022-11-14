# Helpful commands
Commands I use regularly.

#### Open and Save JSON
```python
# Open
f = open('data.json')
data = json.load(f)

# Save
with open(os.path.join(<path>, 'w') as f:
    json.dump(<dict>, f, indent=4, sort_keys=True)

```

#### Imshow
```python
cv2.imshow("window name", out-image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

#### Convert video to images
```bash
$ ffmpeg -i s1v1.avi %06d.png

# Vice versa
$ ffmpeg -i %04d.png output.mp4

# If the filenames don't begin with 0 or have missing indices
$ ffmpeg -framerate 5 -pattern_type glob -i '*.png' out.mp4
```

#### Clip video (order of arguments matter!)
```bash
$ ffmpeg -ss 0 -t 15 -i squats_feedback.mp4 -acodec copy -vcodec copy side_view.mp4
```

#### Crop video
```bash
# out_w is the width of the output rectangle
# out_h is the height of the output rectangle
# x and y specify the top left corner of the output rectangle
$ ffmpeg -i in.mp4 -filter:v "crop=out_w:out_h:x:y" out.mp4

```

#### Recode
```bash
$ ffmpeg -i %06d.png -c:v copy -pix_fmt yuv420p out.mp4
```

#### Leading zeros
```python
"{:04d}.png".format(counter)
```

#### Scan size of /root
```bash
cd /
ncdu -x / 
```


#### Clean tmp
```bash
cd /tmp/
pwd
sudo rm -r *
```

#### Clean logs
```bash
sudo journalctl --vacuum-size=100M
```
