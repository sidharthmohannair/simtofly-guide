# Appendix: Terminal Customization (Optional)

Optional terminal enhancements for advanced users.

**Note:** These customizations are NOT required for SimToFly tutorials. Only apply if you want to personalize your terminal experience.

---

## Enable Color Prompt
```bash
sed -i 's/#force_color_prompt=yes/force_color_prompt=yes/' ~/.bashrc
source ~/.bashrc
```

**Result:** Terminal prompt shows colors.

---

## Add Useful Aliases
```bash
nano ~/.bashrc
```

**Add at bottom:**
```bash
# Useful aliases
alias ll='ls -lah'
alias update='sudo apt update && sudo apt upgrade -y'
alias workspace='cd ~/simtofly_ws'
```

**Save, then:**
```bash
source ~/.bashrc
```

---

## Increase Terminal History
```bash
echo 'HISTSIZE=10000' >> ~/.bashrc
echo 'HISTFILESIZE=20000' >> ~/.bashrc
source ~/.bashrc
```

**Saves last 10,000 commands instead of default 500.**

---

## Show Git Branch in Prompt
```bash
nano ~/.bashrc
```

**Add at bottom:**
```bash
# Show git branch in prompt
parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
export PS1="\u@\h:\w\$(parse_git_branch)\$ "
```

**Save, then:**
```bash
source ~/.bashrc
```

---

[← Back to 1.2 Environment Setup](../phase-1-simulation/1.2-environment-setup.md)
