# 🔄 Custom Subdomain Forwarding with Cloudflare

A simple guide to forward custom subdomains to free Bento and Linktree pages using Cloudflare.

## 🎯 What We're Building

| Subdomain | Forwards To |
|-----------|-------------|
| [iam.nikhilmishra.live](https://iam.nikhilmishra.live) | [bento.me/kaalpanikh](https://bento.me/kaalpanikh) |
| [links.nikhilmishra.live](https://links.nikhilmishra.live) | [linktr.ee/kaalpanikh](https://linktr.ee/kaalpanikh) |

> **Note:** This setup uses Cloudflare as a workaround since free Bento and Linktree plans don't support custom domains.

## 📝 Step-by-Step Guide

### 1️⃣ Create DNS Records

1. Log in to your **Cloudflare Dashboard**
2. Select your domain: `nikhilmishra.live`
3. Go to **DNS** → **Records**
4. Add the following records:

#### For Bento Profile
```
Type: CNAME
Name: iam
Target: @
Proxy: ✅ Enabled (Orange Cloud)
```

#### For Linktree Profile
```
Type: CNAME
Name: links
Target: @
Proxy: ✅ Enabled (Orange Cloud)
```

### 2️⃣ Set Up Page Rules

1. Navigate to **Rules** → **Page Rules**
2. Create two page rules:

#### Bento Redirect
```
URL Pattern: https://iam.nikhilmishra.live/*
Forward to: https://bento.me/kaalpanikh
Status: 301 (Permanent Redirect)
```

#### Linktree Redirect
```
URL Pattern: https://links.nikhilmishra.live/*
Forward to: https://linktr.ee/kaalpanikh
Status: 301 (Permanent Redirect)
```

### 3️⃣ Verify Setup

After DNS propagation (usually 5-10 minutes):

1. Visit [iam.nikhilmishra.live](https://iam.nikhilmishra.live)
   - Should redirect to your Bento profile
2. Visit [links.nikhilmishra.live](https://links.nikhilmishra.live)
   - Should redirect to your Linktree profile

## ⚠️ Troubleshooting

If redirects aren't working:
1. Check if Cloudflare proxy is enabled (orange cloud)
2. Verify page rules are in the correct order
3. Clear your browser cache
4. Wait a few more minutes for DNS propagation

## 🔗 Useful Links

- [Cloudflare Dashboard](https://dash.cloudflare.com)
- [Bento Profile](https://bento.me/kaalpanikh)
- [Linktree Profile](https://linktr.ee/kaalpanikh)
