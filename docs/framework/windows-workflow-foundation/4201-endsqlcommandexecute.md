---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 75c1cdd10aca6b177911bd9d2f51468016eb9e15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774362"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="97d82-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="97d82-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="97d82-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97d82-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97d82-104">ID</span><span class="sxs-lookup"><span data-stu-id="97d82-104">ID</span></span>|<span data-ttu-id="97d82-105">4201</span><span class="sxs-lookup"><span data-stu-id="97d82-105">4201</span></span>|  
|<span data-ttu-id="97d82-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="97d82-106">Keywords</span></span>|<span data-ttu-id="97d82-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="97d82-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="97d82-108">レベル</span><span class="sxs-lookup"><span data-stu-id="97d82-108">Level</span></span>|<span data-ttu-id="97d82-109">詳細</span><span class="sxs-lookup"><span data-stu-id="97d82-109">Verbose</span></span>|  
|<span data-ttu-id="97d82-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="97d82-110">Channel</span></span>|<span data-ttu-id="97d82-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="97d82-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="97d82-112">説明</span><span class="sxs-lookup"><span data-stu-id="97d82-112">Description</span></span>  
 <span data-ttu-id="97d82-113">SQL コマンドの実行が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="97d82-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="97d82-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="97d82-114">Message</span></span>  
 <span data-ttu-id="97d82-115">SQL コマンドの実行を終了します: %1</span><span class="sxs-lookup"><span data-stu-id="97d82-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="97d82-116">説明</span><span class="sxs-lookup"><span data-stu-id="97d82-116">Details</span></span>  
  
|<span data-ttu-id="97d82-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="97d82-117">Data Item Name</span></span>|<span data-ttu-id="97d82-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="97d82-118">Data Item Type</span></span>|<span data-ttu-id="97d82-119">説明</span><span class="sxs-lookup"><span data-stu-id="97d82-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="97d82-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="97d82-120">SqlCommand</span></span>|<span data-ttu-id="97d82-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="97d82-121">xs:string</span></span>|<span data-ttu-id="97d82-122">実行された SQL コマンド。</span><span class="sxs-lookup"><span data-stu-id="97d82-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="97d82-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="97d82-123">AppDomain</span></span>|<span data-ttu-id="97d82-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="97d82-124">xs:string</span></span>|<span data-ttu-id="97d82-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="97d82-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
