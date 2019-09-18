---
title: セキュリティ ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d09b5b76c39f33848d44beb43d9b09c5e6ed13b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046171"
---
# <a name="security-etw-events"></a><span data-ttu-id="09c5b-102">セキュリティ ETW イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="09c5b-103">セキュリティ イベントは、厳密な名前の検証時と Authenticode の検証時に発生します。</span><span class="sxs-lookup"><span data-stu-id="09c5b-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="09c5b-104">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="09c5b-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="09c5b-105">StrongNameVerificationStart_V1 イベントと StrongNameVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="09c5b-106">AuthenticodeVerificationStart_V1 イベントと AuthenticodeVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="09c5b-107">StrongNameVerificationStart_V1 イベントと StrongNameVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="09c5b-108">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="09c5b-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="09c5b-109">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="09c5b-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="09c5b-110">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="09c5b-110">Keyword for raising the event</span></span>|<span data-ttu-id="09c5b-111">レベル</span><span class="sxs-lookup"><span data-stu-id="09c5b-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="09c5b-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="09c5b-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="09c5b-113">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="09c5b-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="09c5b-114">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="09c5b-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="09c5b-115">イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-115">Event</span></span>|<span data-ttu-id="09c5b-116">イベント ID</span><span class="sxs-lookup"><span data-stu-id="09c5b-116">Event ID</span></span>|<span data-ttu-id="09c5b-117">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="09c5b-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="09c5b-118">181</span><span class="sxs-lookup"><span data-stu-id="09c5b-118">181</span></span>|<span data-ttu-id="09c5b-119">厳密な名前の検証の開始。</span><span class="sxs-lookup"><span data-stu-id="09c5b-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="09c5b-120">182</span><span class="sxs-lookup"><span data-stu-id="09c5b-120">182</span></span>|<span data-ttu-id="09c5b-121">厳密な名前の検証の終了。</span><span class="sxs-lookup"><span data-stu-id="09c5b-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="09c5b-122">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="09c5b-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="09c5b-123">フィールド名</span><span class="sxs-lookup"><span data-stu-id="09c5b-123">Field name</span></span>|<span data-ttu-id="09c5b-124">データ型</span><span class="sxs-lookup"><span data-stu-id="09c5b-124">Data type</span></span>|<span data-ttu-id="09c5b-125">説明</span><span class="sxs-lookup"><span data-stu-id="09c5b-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="09c5b-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="09c5b-126">VerificationFlags</span></span>|<span data-ttu-id="09c5b-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="09c5b-127">win:UInt32</span></span>|<span data-ttu-id="09c5b-128">検証フラグ。</span><span class="sxs-lookup"><span data-stu-id="09c5b-128">The verification flags.</span></span>|  
|<span data-ttu-id="09c5b-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="09c5b-129">ErrorCode</span></span>|<span data-ttu-id="09c5b-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="09c5b-130">win:UInt32</span></span>|<span data-ttu-id="09c5b-131">HResult エラー コード。</span><span class="sxs-lookup"><span data-stu-id="09c5b-131">The HResult error code.</span></span>|  
|<span data-ttu-id="09c5b-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="09c5b-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="09c5b-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="09c5b-133">win:UnicodeString</span></span>|<span data-ttu-id="09c5b-134">完全修飾アセンブリ名。</span><span class="sxs-lookup"><span data-stu-id="09c5b-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="09c5b-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="09c5b-135">ClrInstanceID</span></span>|<span data-ttu-id="09c5b-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="09c5b-136">win:UInt16</span></span>|<span data-ttu-id="09c5b-137">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="09c5b-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="09c5b-138">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="09c5b-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="09c5b-139">AuthenticodeVerificationStart_V1 イベントと AuthenticodeVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="09c5b-140">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="09c5b-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="09c5b-141">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="09c5b-141">Keyword for raising the event</span></span>|<span data-ttu-id="09c5b-142">レベル</span><span class="sxs-lookup"><span data-stu-id="09c5b-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="09c5b-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="09c5b-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="09c5b-144">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="09c5b-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="09c5b-145">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="09c5b-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="09c5b-146">イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-146">Event</span></span>|<span data-ttu-id="09c5b-147">イベント ID</span><span class="sxs-lookup"><span data-stu-id="09c5b-147">Event ID</span></span>|<span data-ttu-id="09c5b-148">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="09c5b-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="09c5b-149">183</span><span class="sxs-lookup"><span data-stu-id="09c5b-149">183</span></span>|<span data-ttu-id="09c5b-150">Authenticode 検証の開始。</span><span class="sxs-lookup"><span data-stu-id="09c5b-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="09c5b-151">184</span><span class="sxs-lookup"><span data-stu-id="09c5b-151">184</span></span>|<span data-ttu-id="09c5b-152">Authenticode 検証の終了。</span><span class="sxs-lookup"><span data-stu-id="09c5b-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="09c5b-153">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="09c5b-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="09c5b-154">フィールド名</span><span class="sxs-lookup"><span data-stu-id="09c5b-154">Field name</span></span>|<span data-ttu-id="09c5b-155">データ型</span><span class="sxs-lookup"><span data-stu-id="09c5b-155">Data type</span></span>|<span data-ttu-id="09c5b-156">説明</span><span class="sxs-lookup"><span data-stu-id="09c5b-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="09c5b-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="09c5b-157">VerificationFlags</span></span>|<span data-ttu-id="09c5b-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="09c5b-158">win:UInt32</span></span>|<span data-ttu-id="09c5b-159">検証フラグ。</span><span class="sxs-lookup"><span data-stu-id="09c5b-159">The verification flags.</span></span>|  
|<span data-ttu-id="09c5b-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="09c5b-160">ErrorCode</span></span>|<span data-ttu-id="09c5b-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="09c5b-161">win:UInt32</span></span>|<span data-ttu-id="09c5b-162">HResult エラー コード。</span><span class="sxs-lookup"><span data-stu-id="09c5b-162">The HResult error code.</span></span>|  
|<span data-ttu-id="09c5b-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="09c5b-163">ModulePath</span></span>|<span data-ttu-id="09c5b-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="09c5b-164">win:UnicodeString</span></span>|<span data-ttu-id="09c5b-165">モジュール パス</span><span class="sxs-lookup"><span data-stu-id="09c5b-165">The module path.</span></span>|  
|<span data-ttu-id="09c5b-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="09c5b-166">ClrInstanceID</span></span>|<span data-ttu-id="09c5b-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="09c5b-167">win:UInt16</span></span>|<span data-ttu-id="09c5b-168">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="09c5b-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09c5b-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="09c5b-169">See also</span></span>

- [<span data-ttu-id="09c5b-170">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="09c5b-170">CLR ETW Events</span></span>](clr-etw-events.md)
