---
title: セキュリティ ETW イベント
description: .NET での厳密な名前の検証と Authenticode 検証中に発生するセキュリティ ETW イベントについて説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474216"
---
# <a name="security-etw-events"></a><span data-ttu-id="7bd73-103">セキュリティ ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7bd73-103">Security ETW Events</span></span>

<span data-ttu-id="7bd73-104">セキュリティ イベントは、厳密な名前の検証時と Authenticode の検証時に発生します。</span><span class="sxs-lookup"><span data-stu-id="7bd73-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="7bd73-105">StrongNameVerificationStart_V1 イベントと StrongNameVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7bd73-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="7bd73-106">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7bd73-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="7bd73-107">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7bd73-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="7bd73-108">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7bd73-108">Keyword for raising the event</span></span>|<span data-ttu-id="7bd73-109">Level</span><span class="sxs-lookup"><span data-stu-id="7bd73-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7bd73-110">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="7bd73-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="7bd73-111">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="7bd73-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="7bd73-112">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7bd73-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7bd73-113">Event</span><span class="sxs-lookup"><span data-stu-id="7bd73-113">Event</span></span>|<span data-ttu-id="7bd73-114">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7bd73-114">Event ID</span></span>|<span data-ttu-id="7bd73-115">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7bd73-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="7bd73-116">181</span><span class="sxs-lookup"><span data-stu-id="7bd73-116">181</span></span>|<span data-ttu-id="7bd73-117">厳密な名前の検証の開始。</span><span class="sxs-lookup"><span data-stu-id="7bd73-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="7bd73-118">182</span><span class="sxs-lookup"><span data-stu-id="7bd73-118">182</span></span>|<span data-ttu-id="7bd73-119">厳密な名前の検証の終了。</span><span class="sxs-lookup"><span data-stu-id="7bd73-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="7bd73-120">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7bd73-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7bd73-121">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7bd73-121">Field name</span></span>|<span data-ttu-id="7bd73-122">データ型</span><span class="sxs-lookup"><span data-stu-id="7bd73-122">Data type</span></span>|<span data-ttu-id="7bd73-123">説明</span><span class="sxs-lookup"><span data-stu-id="7bd73-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7bd73-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="7bd73-124">VerificationFlags</span></span>|<span data-ttu-id="7bd73-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7bd73-125">win:UInt32</span></span>|<span data-ttu-id="7bd73-126">検証フラグ。</span><span class="sxs-lookup"><span data-stu-id="7bd73-126">The verification flags.</span></span>|  
|<span data-ttu-id="7bd73-127">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="7bd73-127">ErrorCode</span></span>|<span data-ttu-id="7bd73-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7bd73-128">win:UInt32</span></span>|<span data-ttu-id="7bd73-129">HResult エラー コード。</span><span class="sxs-lookup"><span data-stu-id="7bd73-129">The HResult error code.</span></span>|  
|<span data-ttu-id="7bd73-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7bd73-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="7bd73-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7bd73-131">win:UnicodeString</span></span>|<span data-ttu-id="7bd73-132">完全修飾アセンブリ名。</span><span class="sxs-lookup"><span data-stu-id="7bd73-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="7bd73-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7bd73-133">ClrInstanceID</span></span>|<span data-ttu-id="7bd73-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7bd73-134">win:UInt16</span></span>|<span data-ttu-id="7bd73-135">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7bd73-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="7bd73-136">AuthenticodeVerificationStart_V1 イベントと AuthenticodeVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7bd73-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="7bd73-137">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7bd73-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="7bd73-138">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7bd73-138">Keyword for raising the event</span></span>|<span data-ttu-id="7bd73-139">Level</span><span class="sxs-lookup"><span data-stu-id="7bd73-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7bd73-140">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="7bd73-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="7bd73-141">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="7bd73-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="7bd73-142">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7bd73-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7bd73-143">Event</span><span class="sxs-lookup"><span data-stu-id="7bd73-143">Event</span></span>|<span data-ttu-id="7bd73-144">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7bd73-144">Event ID</span></span>|<span data-ttu-id="7bd73-145">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7bd73-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="7bd73-146">183</span><span class="sxs-lookup"><span data-stu-id="7bd73-146">183</span></span>|<span data-ttu-id="7bd73-147">Authenticode 検証の開始。</span><span class="sxs-lookup"><span data-stu-id="7bd73-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="7bd73-148">184</span><span class="sxs-lookup"><span data-stu-id="7bd73-148">184</span></span>|<span data-ttu-id="7bd73-149">Authenticode 検証の終了。</span><span class="sxs-lookup"><span data-stu-id="7bd73-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="7bd73-150">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7bd73-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7bd73-151">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7bd73-151">Field name</span></span>|<span data-ttu-id="7bd73-152">データ型</span><span class="sxs-lookup"><span data-stu-id="7bd73-152">Data type</span></span>|<span data-ttu-id="7bd73-153">説明</span><span class="sxs-lookup"><span data-stu-id="7bd73-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7bd73-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="7bd73-154">VerificationFlags</span></span>|<span data-ttu-id="7bd73-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7bd73-155">win:UInt32</span></span>|<span data-ttu-id="7bd73-156">検証フラグ。</span><span class="sxs-lookup"><span data-stu-id="7bd73-156">The verification flags.</span></span>|  
|<span data-ttu-id="7bd73-157">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="7bd73-157">ErrorCode</span></span>|<span data-ttu-id="7bd73-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7bd73-158">win:UInt32</span></span>|<span data-ttu-id="7bd73-159">HResult エラー コード。</span><span class="sxs-lookup"><span data-stu-id="7bd73-159">The HResult error code.</span></span>|  
|<span data-ttu-id="7bd73-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="7bd73-160">ModulePath</span></span>|<span data-ttu-id="7bd73-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7bd73-161">win:UnicodeString</span></span>|<span data-ttu-id="7bd73-162">モジュール パス</span><span class="sxs-lookup"><span data-stu-id="7bd73-162">The module path.</span></span>|  
|<span data-ttu-id="7bd73-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7bd73-163">ClrInstanceID</span></span>|<span data-ttu-id="7bd73-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7bd73-164">win:UInt16</span></span>|<span data-ttu-id="7bd73-165">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7bd73-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7bd73-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bd73-166">See also</span></span>

- [<span data-ttu-id="7bd73-167">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7bd73-167">CLR ETW Events</span></span>](clr-etw-events.md)
