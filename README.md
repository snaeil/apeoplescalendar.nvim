<div align="center">

# apeoplescalendar.nvim

[About](#about) • [Install](#install) • [Usage](#usage) • [Contribute](#contribute)

</div>

---

This Neovim plugin is written in Lua and provides daily information from [apeoplescalendar.org](https://www.apeoplescalendar.org/).

## About

From [apeoplescalendar.org](https://www.apeoplescalendar.org):

> A People's Calendar (aPC) is a project that seeks to promote the worldwide history of working class movements and liberation struggles in the form of a searchable "On This Day" calendar.
> aPC was inspired by historian Howard Zinn's work "A People's History of the United States". Zinn's scholarship and political activism demonstrated the power of mass working class movements, as well as the critical importance of knowing this history when we seek to change the present.
> The greatest experts on any historical event or struggle will always be the people who live it, as well as the scholars who document it meticulously. Our ambition is to promote awareness of this history while emphasizing these perspectives.

## Install

This example should Using lazy you can use this:

```lua
{
	"snaeil/apeoplescalendar.nvim",
	dependencies = {
		"rcarriga/nvim-notify",
	},
    name = "apeoplescalendar",
}
```

### Requirements

- Linux or Mac operating system
- Neovim 0.7+
- Plugin [rcarriga/nvim-notify](https://github.com/rcarriga/nvim-notify)
- curl

## Usage

**`:APeoplesCalendar`**

Opens a new buffer showing today's events. In normal mode it can be closed with key `q`.

**`:APeoplesCalendarTeaser`**

Opens a popup with one randomly picked event for today's date. It disappears automatically after a few seconds.

### Configuration

With this example, the teaser should be shown every time Neovim is opened without specifying a file.

```lua
{
	"snaeil/apeoplescalendar.nvim",
	dependencies = {
		"rcarriga/nvim-notify",
	},
    event = "VeryLazy",
    name = "apeoplescalendar",
    config = function ()
        local vim_args = #vim.v.argv
        if (vim_args < 3) then
            require("apeoplescalendar").today_teaser()
        end
    end,
}
```

## Contribute

A People's Calendar is [open source](https://github.com/aPeoplesCalendar/apc-web).
