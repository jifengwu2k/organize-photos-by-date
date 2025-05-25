# Organize Photos by Date

Organize and copy your photos into folders by their shooting date (from EXIF metadata).

## Features

- Reads shooting date from image EXIF data
- Organizes images into folders by year and by date (e.g. `2024/2024-06-08/`)
- Preserves file attributes while copying
- Supports dry run and verbose output modes

## Requirements

- Python 3.5+
- [exifread](https://pypi.org/project/ExifRead/)

Install dependencies:
```bash
pip install exifread
```

## Usage

```bash
python organize_photos_by_date.py [options] <source_dir> <target_dir>
```

**Options:**
- `-v`, `--verbose` : Show verbose output
- `-d`, `--dry-run`: Simulate actions but don't perform copy

**Example:**

```bash
python organize_photos_by_date.py -v ~/Pictures ~/OrganizedPhotos
```
Dry run mode:
```bash
python organize_photos_by_date.py -v -d ~/Pictures ~/OrganizedPhotos
```

## Notes

- Only files with common image extensions (`.jpg`, `.jpeg`, `.tif`, `.tiff`, `.png`, `.heic`) are processed.
- If EXIF shooting date is missing, the file will be skipped (with a warning).

## License

MIT License