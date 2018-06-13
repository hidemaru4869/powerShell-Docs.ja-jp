---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ソーシャル メディアやコメントを使用したフィードバックの提供
ms.openlocfilehash: a8e6097de4a565b504189b0b0488c45b6d78a8b6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="providing-feedback-via-social-media-or-comments"></a><span data-ttu-id="50d26-103">ソーシャル メディアやコメントを使用したフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="50d26-103">Providing Feedback via social media or comments</span></span>

<span data-ttu-id="50d26-104">PowerShell ギャラリーでは、ユーザーがアイテムへのパブリック フィードバックを提供する 2 つの方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50d26-104">The Powershell Gallery supports two approaches for users to provide public feedback on an item:</span></span>

- <span data-ttu-id="50d26-105">左端のリンクを使用して、Facebook、LinkedIn、Twitter などのソーシャル メディア サイト内でアイテムを "共有" する。</span><span class="sxs-lookup"><span data-stu-id="50d26-105">Use the links on the left edge to "share" an item in Facebook, LinkedIn, or Twitter social media sites;</span></span>
- <span data-ttu-id="50d26-106">コメント機能を使用してユーザーがアイテムへのコメントを投稿し、作成者は公開しているアイテムへのコメントを確認する。</span><span class="sxs-lookup"><span data-stu-id="50d26-106">Use the Comment feature to post comments on an item, and to allow Authors to watch for comments on items they publish.</span></span>

## <a name="social-media-feedback"></a><span data-ttu-id="50d26-107">ソーシャル メディア フィードバック</span><span class="sxs-lookup"><span data-stu-id="50d26-107">Social Media Feedback</span></span>

<span data-ttu-id="50d26-108">PowerShell ギャラリー内にある各アイテムのページの左側には、Facebook、LinkedIn、Twitter のリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="50d26-108">On the left side of the page for each item in the PowerShell Gallery there are links for Facebook, LinkedIn, and Twitter.</span></span>
<span data-ttu-id="50d26-109">これらのリンクをクリックすることでソーシャル メディア サイトが開き、アイテムへのリンクをすぐに共有できます。</span><span class="sxs-lookup"><span data-stu-id="50d26-109">Clicking on these links will open the social media site, and allow quickly sharing a link to the item.</span></span>

<span data-ttu-id="50d26-110">ユーザーが PowerShell ギャラリーのアイテムを共有するには、選択したサイトにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d26-110">Users must log in to the site they have chosen in order to share the PowerShell Gallery item.</span></span>

<span data-ttu-id="50d26-111">他のユーザーに勧めたいアイテムを見つけた場合も、こうすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="50d26-111">Users are encouraged to do this if they find that an item is something they would recommend to others.</span></span>
<span data-ttu-id="50d26-112">PowerShell ギャラリーでは、アイテムの "共有" について各ソーシャル メディア サイトを確認し、各ソーシャル メディア サイト内でアイテムが共有された回数を表示します。</span><span class="sxs-lookup"><span data-stu-id="50d26-112">The PowerShell Gallery will check each social media site for "shares" of the item, and display how many times that item has been shared in each of the social media sites.</span></span>
<span data-ttu-id="50d26-113">これにより、アイテムが共有された回数のみが表示されるため、他のユーザーからは "いいね!" と評価されたアイテムであると解釈されます。</span><span class="sxs-lookup"><span data-stu-id="50d26-113">Since this shows only the count of times something has been shared, it will be intepreted other users as "liking" the item.</span></span>


## <a name="comments"></a><span data-ttu-id="50d26-114">備考</span><span class="sxs-lookup"><span data-stu-id="50d26-114">Comments</span></span>

<span data-ttu-id="50d26-115">PowerShell ギャラリーでは LiveFyre サービスを使用しており、ユーザーはアイテムに対するコメントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="50d26-115">The PowerShell Gallery uses the LiveFyre service to allow users to comment on items.</span></span>
<span data-ttu-id="50d26-116">推奨したいものやフィードバックがあるユーザーはこの機能を使用することで、アイテムのページを訪れる人が見ることのできるフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="50d26-116">Users who have recommendations or feedback can use this feature to provide feedback that is visible to anyone who visits the item page.</span></span>
<span data-ttu-id="50d26-117">アイテムの所有者はこのフィードバックをフォローして、コメントが投稿されたときに通知されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="50d26-117">Item owners can Follow this feedback, and be notified when someone posts a comment.</span></span>

<span data-ttu-id="50d26-118">コメント システムは LiveFyre に基づいています。このサービスは、Microsoft が管理するものではない独自サービスのため、使用には別途ログインが必要になります。</span><span class="sxs-lookup"><span data-stu-id="50d26-118">The Comment system is based on LiveFyre, which is a separate service that is not managed by Microsoft, and requires unique login to use.</span></span>
<span data-ttu-id="50d26-119">アイテムにコメントする、または自分のアイテムへのコメントをフォローすることを選択する場合、初回は LiveFyre アカウントを作成するためのダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50d26-119">The first time you choose to leave a comment or Follow comments on one of your items, you will be prompted to create a LiveFyre account.</span></span>

<span data-ttu-id="50d26-120">LiveFyre アカウントを作成してログインすると、アイテムにフィードバックするコメントを作成できます。次に [Post comment...]\(コメントを投稿する\)をクリックします。コメントはすぐには表示されません。</span><span class="sxs-lookup"><span data-stu-id="50d26-120">If you have created a LiveFyre account and logged in, you can craft a comment that provides feedback on the item, then click on "Post comment..." The comment will not be visible immediately.</span></span>
<span data-ttu-id="50d26-121">ギャラリーのアイテムに関するコメントは PowerShell ギャラリーの管理者によって管理されており、すべての投稿はモデレーターによる確認の後に公開されて、他のユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="50d26-121">Comments for gallery items are moderated by the PowerShell Gallery administrators, and all posts are reviewed by the moderators before being published and visible to others.</span></span>
<span data-ttu-id="50d26-122">コメントを管理する目的は、コメントの内容が、PowerShell ギャラリーの[使用条件](https://www.powershellgallery.com/policies/Terms)に準拠した公的な振る舞いになっているかを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="50d26-122">Our purpose in moderating the comments is to ensure that they align with public behavior consistent with the PowerShell Gallery [Terms of Use](https://www.powershellgallery.com/policies/Terms).</span></span>

<span data-ttu-id="50d26-123">アイテムの所有者は LiveFyre に投稿されたコメントをフォローすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="50d26-123">Item owners are encouraged to Follow comments that are posted to LiveFyre.</span></span>
<span data-ttu-id="50d26-124">LiveFyre アカウントが必要です。LiveFyre でアイテムを公開する際に用いる電子メール アドレスと同じものを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="50d26-124">A LiveFyre account is required, and it is recommended to use the same email address you use for publishing your item in LiveFyre.</span></span>
<span data-ttu-id="50d26-125">コメントをフォローするには、LiveFyre にログインし、所有者として表示されているアイテムのいずれかに移動します。</span><span class="sxs-lookup"><span data-stu-id="50d26-125">To Follow comments, log into LiveFyre, and navigate to any item where you are listed as an Owner.</span></span>
<span data-ttu-id="50d26-126">各アイテムの下部にある [Comment]\(コメント\) ボックスの下に、[+Follow]\(フォロー\) と表示されています。</span><span class="sxs-lookup"><span data-stu-id="50d26-126">Below the Comment box at the bottom of each item you will see "+Follow".</span></span>
<span data-ttu-id="50d26-127">これをクリックすると、アイテムに新しいコメントが作成されるたびに、登録されている電子メール アドレスに LiveFyre から電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="50d26-127">Once you click on this, LiveFyre will send an email to the registered email address any time new comments made on the item.</span></span>