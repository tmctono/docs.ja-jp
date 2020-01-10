---
title: セキュリティ ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715937"
---
# <a name="security-etw-events"></a><span data-ttu-id="3cbc9-102">セキュリティ ETW イベント</span><span class="sxs-lookup"><span data-stu-id="3cbc9-102">Security ETW Events</span></span>

<span data-ttu-id="3cbc9-103">セキュリティ イベントは、厳密な名前の検証時と Authenticode の検証時に発生します。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="3cbc9-104">StrongNameVerificationStart_V1 イベントと StrongNameVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="3cbc9-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="3cbc9-105">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="3cbc9-106">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="3cbc9-107">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="3cbc9-107">Keyword for raising the event</span></span>|<span data-ttu-id="3cbc9-108">レベル</span><span class="sxs-lookup"><span data-stu-id="3cbc9-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="3cbc9-109">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="3cbc9-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="3cbc9-110">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="3cbc9-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="3cbc9-111">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="3cbc9-112">Event</span><span class="sxs-lookup"><span data-stu-id="3cbc9-112">Event</span></span>|<span data-ttu-id="3cbc9-113">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3cbc9-113">Event ID</span></span>|<span data-ttu-id="3cbc9-114">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="3cbc9-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="3cbc9-115">181</span><span class="sxs-lookup"><span data-stu-id="3cbc9-115">181</span></span>|<span data-ttu-id="3cbc9-116">厳密な名前の検証の開始。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="3cbc9-117">182</span><span class="sxs-lookup"><span data-stu-id="3cbc9-117">182</span></span>|<span data-ttu-id="3cbc9-118">厳密な名前の検証の終了。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="3cbc9-119">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="3cbc9-120">フィールド名</span><span class="sxs-lookup"><span data-stu-id="3cbc9-120">Field name</span></span>|<span data-ttu-id="3cbc9-121">[データ型]</span><span class="sxs-lookup"><span data-stu-id="3cbc9-121">Data type</span></span>|<span data-ttu-id="3cbc9-122">説明</span><span class="sxs-lookup"><span data-stu-id="3cbc9-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="3cbc9-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="3cbc9-123">VerificationFlags</span></span>|<span data-ttu-id="3cbc9-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3cbc9-124">win:UInt32</span></span>|<span data-ttu-id="3cbc9-125">検証フラグ。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-125">The verification flags.</span></span>|  
|<span data-ttu-id="3cbc9-126">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="3cbc9-126">ErrorCode</span></span>|<span data-ttu-id="3cbc9-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3cbc9-127">win:UInt32</span></span>|<span data-ttu-id="3cbc9-128">HResult エラー コード。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-128">The HResult error code.</span></span>|  
|<span data-ttu-id="3cbc9-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="3cbc9-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="3cbc9-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="3cbc9-130">win:UnicodeString</span></span>|<span data-ttu-id="3cbc9-131">完全修飾アセンブリ名。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="3cbc9-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="3cbc9-132">ClrInstanceID</span></span>|<span data-ttu-id="3cbc9-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3cbc9-133">win:UInt16</span></span>|<span data-ttu-id="3cbc9-134">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="3cbc9-135">AuthenticodeVerificationStart_V1 イベントと AuthenticodeVerificationStop_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="3cbc9-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="3cbc9-136">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="3cbc9-137">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="3cbc9-137">Keyword for raising the event</span></span>|<span data-ttu-id="3cbc9-138">レベル</span><span class="sxs-lookup"><span data-stu-id="3cbc9-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="3cbc9-139">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="3cbc9-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="3cbc9-140">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="3cbc9-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="3cbc9-141">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="3cbc9-142">Event</span><span class="sxs-lookup"><span data-stu-id="3cbc9-142">Event</span></span>|<span data-ttu-id="3cbc9-143">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3cbc9-143">Event ID</span></span>|<span data-ttu-id="3cbc9-144">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="3cbc9-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="3cbc9-145">183</span><span class="sxs-lookup"><span data-stu-id="3cbc9-145">183</span></span>|<span data-ttu-id="3cbc9-146">Authenticode 検証の開始。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="3cbc9-147">184</span><span class="sxs-lookup"><span data-stu-id="3cbc9-147">184</span></span>|<span data-ttu-id="3cbc9-148">Authenticode 検証の終了。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="3cbc9-149">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="3cbc9-150">フィールド名</span><span class="sxs-lookup"><span data-stu-id="3cbc9-150">Field name</span></span>|<span data-ttu-id="3cbc9-151">[データ型]</span><span class="sxs-lookup"><span data-stu-id="3cbc9-151">Data type</span></span>|<span data-ttu-id="3cbc9-152">説明</span><span class="sxs-lookup"><span data-stu-id="3cbc9-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="3cbc9-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="3cbc9-153">VerificationFlags</span></span>|<span data-ttu-id="3cbc9-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3cbc9-154">win:UInt32</span></span>|<span data-ttu-id="3cbc9-155">検証フラグ。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-155">The verification flags.</span></span>|  
|<span data-ttu-id="3cbc9-156">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="3cbc9-156">ErrorCode</span></span>|<span data-ttu-id="3cbc9-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="3cbc9-157">win:UInt32</span></span>|<span data-ttu-id="3cbc9-158">HResult エラー コード。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-158">The HResult error code.</span></span>|  
|<span data-ttu-id="3cbc9-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="3cbc9-159">ModulePath</span></span>|<span data-ttu-id="3cbc9-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="3cbc9-160">win:UnicodeString</span></span>|<span data-ttu-id="3cbc9-161">モジュールのパス。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-161">The module path.</span></span>|  
|<span data-ttu-id="3cbc9-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="3cbc9-162">ClrInstanceID</span></span>|<span data-ttu-id="3cbc9-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="3cbc9-163">win:UInt16</span></span>|<span data-ttu-id="3cbc9-164">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="3cbc9-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3cbc9-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cbc9-165">See also</span></span>

- [<span data-ttu-id="3cbc9-166">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="3cbc9-166">CLR ETW Events</span></span>](clr-etw-events.md)
