# Contributing to NSW Fire Danger Ratings

Thank you for your interest in contributing! 🎉

## How to Contribute

### Reporting Bugs

If you find a bug, please create an issue on GitHub with:
- Description of the bug
- Steps to reproduce
- Expected behavior
- Actual behavior
- Home Assistant version
- Integration version
- Relevant logs

### Suggesting Features

Feature requests are welcome! Please create an issue describing:
- The feature you'd like to see
- Why it would be useful
- How it might work

### Pull Requests

1. Fork the repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test thoroughly
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

### Code Style

- Follow Home Assistant's [development guidelines](https://developers.home-assistant.io/)
- Use Python Black for formatting
- Add comments for complex logic
- Update documentation for new features

### Testing

- Test with multiple fire weather areas
- Verify the custom card works on desktop and mobile
- Check that sensors update correctly
- Ensure configuration flow works properly

## Development Setup

1. Clone the repository
2. Create a symlink to your Home Assistant `custom_components` directory
3. Restart Home Assistant
4. Enable debug logging in `configuration.yaml`:

```yaml
logger:
  default: info
  logs:
    custom_components.nsw_fire_danger: debug
```

## Questions?

Feel free to open a discussion on GitHub!

## Code of Conduct

Be respectful, inclusive, and collaborative. We're all here to make Home Assistant better!
