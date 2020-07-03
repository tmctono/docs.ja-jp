---
title: IPv6 アドレス指定
description: インターネット プロトコル バージョン 6 (IPv6) のアドレス (テキスト表現やアドレスの種類など) について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- Internet Protocol version 6, addresses in
- Neighbor Discovery
- IPv6, enabling
- IPv6, mobility and
- Internet Protocol version 6, anycast addresses
- IPv6, Neighbor Discovery
- Internet Protocol version 6, auto-configuring
- Internet Protocol version 6, enabling
- IPv6, unicast addresses
- IPv6, auto-configuring
- Internet Protocol version 6, routing
- IPv6, RFC documents
- IPv6, routing
- Internet Protocol version 6, disabling
- Internet Protocol version 6, unicast addresses
- IPv6, multicast addresses
- Internet Protocol version 6, mobility and
- Internet Protocol version 6, RFC documents
- Internet Protocol version 6, Neighbor Discovery
- IPv6, anycast addresses
- Internet Protocol version 6, multicast addresses
- IPv6, addresses in
- IPv6, disabling
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
ms.openlocfilehash: fbf68cb5f40450c2f9ecf4900801ee55e326fcb4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502341"
---
# <a name="ipv6-addressing"></a><span data-ttu-id="2b3cf-103">IPv6 アドレス指定</span><span class="sxs-lookup"><span data-stu-id="2b3cf-103">IPv6 Addressing</span></span>

<span data-ttu-id="2b3cf-104">インターネット プロトコル バージョン 6 (IPv6) では、アドレスの長さは 128 ビットです。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-104">In the Internet Protocol version 6 (IPv6), addresses are 128 bits long.</span></span> <span data-ttu-id="2b3cf-105">このような大きいアドレス空間の 1 つの理由は、インターネットのトポロジを反映したルーティング ドメインの階層構造に利用可能なアドレスを細分化するためです。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-105">One reason for such a large address space is to subdivide the available addresses into a hierarchy of routing domains that reflect the Internet's topology.</span></span> <span data-ttu-id="2b3cf-106">別の理由は、ネットワークにデバイスを接続するネットワーク アダプター (インターフェイス) のアドレスをマップするためです。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-106">Another reason is to map the addresses of network adapters (or interfaces) that connect devices to the network.</span></span> <span data-ttu-id="2b3cf-107">IPv6 は、ネットワーク インターフェイス レベルである最下位レベルでアドレスを解決する固有の機能、および自動構成機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-107">IPv6 features an inherent capability to resolve addresses at their lowest level, which is at the network interface level, and also has auto-configuration capabilities.</span></span>

## <a name="text-representation"></a><span data-ttu-id="2b3cf-108">テキスト表現</span><span class="sxs-lookup"><span data-stu-id="2b3cf-108">Text Representation</span></span>

<span data-ttu-id="2b3cf-109">IPv6 アドレスをテキスト文字列として表すために使用する 3 つの従来型形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-109">The following are the three conventional forms used to represent the IPv6 addresses as text strings:</span></span>

- <span data-ttu-id="2b3cf-110">**コロン 16 進数形式**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-110">**Colon-hexadecimal form**.</span></span> <span data-ttu-id="2b3cf-111">これは、優先される形式 (n:n:n:n:n:n:n:n) です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-111">This is the preferred form n:n:n:n:n:n:n:n.</span></span> <span data-ttu-id="2b3cf-112">各 n は、アドレスの 8 つの 16 ビット要素の 1 つの 16 進数の値を表します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-112">Each n represents the hexadecimal value of one of the eight 16-bit elements of the address.</span></span> <span data-ttu-id="2b3cf-113">たとえば、`3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-113">For example: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.</span></span>

- <span data-ttu-id="2b3cf-114">**圧縮形式**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-114">**Compressed form**.</span></span> <span data-ttu-id="2b3cf-115">アドレスの長さのために、アドレスが 0 の長い文字列を含むのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-115">Due to the address length, it is common to have addresses containing a long string of zeros.</span></span> <span data-ttu-id="2b3cf-116">これらのアドレスの記述を簡略化するために、0 ブロックの 1 つの連続するシーケンスがダブル コロン記号 (:) で表される圧縮形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-116">To simplify writing these addresses, use the compressed form, in which a single contiguous sequence of 0 blocks are represented by a double-colon symbol (::).</span></span> <span data-ttu-id="2b3cf-117">この記号は、アドレスで 1 回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-117">This symbol can appear only once in an address.</span></span> <span data-ttu-id="2b3cf-118">たとえば、マルチキャスト アドレス `FFED:0:0:0:0:BA98:3210:4562` の圧縮形式は `FFED::BA98:3210:4562` です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-118">For example, the multicast address `FFED:0:0:0:0:BA98:3210:4562` in compressed form is `FFED::BA98:3210:4562`.</span></span> <span data-ttu-id="2b3cf-119">ユニキャスト アドレス `3FFE:FFFF:0:0:8:800:20C4:0` の圧縮形式は `3FFE:FFFF::8:800:20C4:0` です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-119">The unicast address `3FFE:FFFF:0:0:8:800:20C4:0` in compressed form is `3FFE:FFFF::8:800:20C4:0`.</span></span> <span data-ttu-id="2b3cf-120">ループバック アドレス `0:0:0:0:0:0:0:1` の圧縮形式は `::`1 です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-120">The loopback address `0:0:0:0:0:0:0:1` in compressed form is `::`1.</span></span> <span data-ttu-id="2b3cf-121">未指定アドレス `0:0:0:0:0:0:0:0` の圧縮形式は `::` です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-121">The unspecified address `0:0:0:0:0:0:0:0` in compressed form is `::`.</span></span>

- <span data-ttu-id="2b3cf-122">**混在形式**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-122">**Mixed form**.</span></span> <span data-ttu-id="2b3cf-123">この形式は、IPv4 アドレスと IPv6 アドレスを結合します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-123">This form combines IPv4 and IPv6 addresses.</span></span> <span data-ttu-id="2b3cf-124">この場合、アドレス形式は n:n:n:n:n:n:d.d.d.d です。ここで、各 n は 6 つの IPv6 上位 16 ビットのアドレス要素の 16 進数値を表し、各 d は、IPv4 アドレスの 10 進数値を表します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-124">In this case, the address format is n:n:n:n:n:n:d.d.d.d, where each n represents the hexadecimal values of the six IPv6 high-order 16-bit address elements, and each d represents the decimal value of an IPv4 address.</span></span>

## <a name="address-types"></a><span data-ttu-id="2b3cf-125">アドレスの種類</span><span class="sxs-lookup"><span data-stu-id="2b3cf-125">Address Types</span></span>

<span data-ttu-id="2b3cf-126">アドレスの先頭のビットは、特定の IPv6 アドレスの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-126">The leading bits in the address define the specific IPv6 address type.</span></span> <span data-ttu-id="2b3cf-127">これらの先頭のビットを含む可変長のフィールドは、フォーマット プレフィックス (FP) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-127">The variable-length field containing these leading bits is called a Format Prefix (FP).</span></span>

<span data-ttu-id="2b3cf-128">IPv6 ユニキャスト アドレスは、2 つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-128">An IPv6 unicast address is divided into two parts.</span></span> <span data-ttu-id="2b3cf-129">最初の部分には、アドレス プレフィックスが含まれており、2 番目の部分にはインターフェイス識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-129">The first part contains the address prefix, and the second part contains the interface identifier.</span></span> <span data-ttu-id="2b3cf-130">IPv6 アドレス/プレフィックスの組み合わせを表現するための簡潔な方法は、ipv6 アドレス/プレフィックス長です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-130">A concise way to express an IPv6 address/prefix combination is as follows: ipv6-address/prefix-length.</span></span>

<span data-ttu-id="2b3cf-131">64 ビットのプレフィックスを使用するアドレスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-131">The following is an example of an address with a 64-bit prefix.</span></span>

<span data-ttu-id="2b3cf-132">`3FFE:FFFF:0:CD30:0:0:0:0/64`。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-132">`3FFE:FFFF:0:CD30:0:0:0:0/64`.</span></span>

<span data-ttu-id="2b3cf-133">この例のプレフィックスは `3FFE:FFFF:0:CD30` です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-133">The prefix in this example is `3FFE:FFFF:0:CD30`.</span></span> <span data-ttu-id="2b3cf-134">アドレスは、`3FFE:FFFF:0:CD30::/64` のように圧縮形式で書き込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-134">The address can also be written in a compressed form, as `3FFE:FFFF:0:CD30::/64`.</span></span>

<span data-ttu-id="2b3cf-135">IPv6 では、次のアドレスの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-135">IPv6 defines the following address types:</span></span>

- <span data-ttu-id="2b3cf-136">**ユニキャスト アドレス**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-136">**Unicast address**.</span></span> <span data-ttu-id="2b3cf-137">1 つのインターフェイスの識別子。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-137">An identifier for a single interface.</span></span> <span data-ttu-id="2b3cf-138">このアドレスに送信されるパケットは、識別されたインターフェイスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-138">A packet sent to this address is delivered to the identified interface.</span></span> <span data-ttu-id="2b3cf-139">ユニキャスト アドレスは、上位のオクテットによってマルチキャスト アドレスと区別されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-139">The unicast addresses are distinguished from the multicast addresses by the value of the high-order octet.</span></span> <span data-ttu-id="2b3cf-140">マルチキャスト アドレスの上位のオクテットには、FF の 16 進数値があります。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-140">The multicast addresses' high-order octet has the hexadecimal value of FF.</span></span> <span data-ttu-id="2b3cf-141">このオクテットの他のすべての値は、ユニキャスト アドレスであることを示します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-141">Any other value for this octet identifies a unicast address.</span></span> <span data-ttu-id="2b3cf-142">ユニキャスト アドレスの種類を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-142">The following are different types of unicast addresses:</span></span>

  - <span data-ttu-id="2b3cf-143">**リンクローカル アドレス**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-143">**Link-local addresses**.</span></span> <span data-ttu-id="2b3cf-144">これらのアドレスは 1 つのリンクで使用され、形式は FE80::*InterfaceID* です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-144">These addresses are used on a single link and have the following format: FE80::*InterfaceID*.</span></span> <span data-ttu-id="2b3cf-145">リンク ローカル アドレスは、自動アドレス構成、近隣探索、またはルーターが存在しない場合に、リンク上のノード間で使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-145">Link-local addresses are used between nodes on a link for auto-address configuration, neighbor discovery, or when no routers are present.</span></span> <span data-ttu-id="2b3cf-146">リンク ローカル アドレスは、主に起動時に、システムが大きい範囲のアドレスをまだ取得していないときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-146">A link-local address is used primarily at startup and when the system has not yet acquired addresses of larger scope.</span></span>

  - <span data-ttu-id="2b3cf-147">**サイトローカル アドレス**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-147">**Site-local addresses**.</span></span> <span data-ttu-id="2b3cf-148">これらのアドレスは、1 つのサイトで使用され、形式は FEC0::*SubnetID*:*InterfaceID* です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-148">These addresses are used on a single site and have the following format: FEC0::*SubnetID*:*InterfaceID*.</span></span> <span data-ttu-id="2b3cf-149">サイト ローカル アドレスは、グローバル プレフィックスが必要ないサイト内でのアドレス指定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-149">The site-local addresses are used for addressing inside a site without the need for a global prefix.</span></span>

  - <span data-ttu-id="2b3cf-150">**グローバル IPv6 ユニキャスト アドレス**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-150">**Global IPv6 unicast addresses**.</span></span> <span data-ttu-id="2b3cf-151">これらのアドレスは、インターネット経由で使用可能であり、形式は 010 (FP、3 ビット) TLA ID (13 ビット) 予約済み (8 ビット) NLA ID (24 ビット) SLA ID (16 ビット) *InterfaceID* (64 ビット) です。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-151">These addresses can be used across the Internet and have the following format: 010(FP, 3 bits) TLA ID (13 bits) Reserved (8 bits) NLA ID (24 bits) SLA ID (16 bits) *InterfaceID* (64 bits).</span></span>

- <span data-ttu-id="2b3cf-152">**マルチキャスト アドレス**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-152">**Multicast address**.</span></span> <span data-ttu-id="2b3cf-153">(通常は別々のノードに属する) インターフェイスのセットの識別子。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-153">An identifier for a set of interfaces (typically belonging to different nodes).</span></span> <span data-ttu-id="2b3cf-154">このアドレスに送信されるパケットは、アドレスで識別されたすべてのインターフェイスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-154">A packet sent to this address is delivered to all the interfaces identified by the address.</span></span> <span data-ttu-id="2b3cf-155">マルチキャスト アドレスの種類は、IPv4 ブロードキャスト アドレスよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-155">The multicast address types supersede the IPv4 broadcast addresses.</span></span>

- <span data-ttu-id="2b3cf-156">**エニーキャスト アドレス**。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-156">**Anycast address**.</span></span> <span data-ttu-id="2b3cf-157">(通常は別々のノードに属する) インターフェイスのセットの識別子。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-157">An identifier for a set of interfaces (typically belonging to different nodes).</span></span> <span data-ttu-id="2b3cf-158">このアドレスに送信されるパケットは、アドレスで識別された 1 つのインターフェイスのみに配信されます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-158">A packet sent to this address is delivered to only one interface identified by the address.</span></span> <span data-ttu-id="2b3cf-159">これは、ルーティング メトリックで識別される最も近いインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-159">This is the nearest interface as identified by routing metrics.</span></span> <span data-ttu-id="2b3cf-160">エニーキャスト アドレスは、ユニキャスト アドレス空間からが取得されるため、構文的に区別できません。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-160">Anycast addresses are taken from the unicast address space and are not syntactically distinguishable.</span></span> <span data-ttu-id="2b3cf-161">アドレス指定されたインターフェイスは、構成の機能として、ユニキャスト アドレスとエニーキャスト アドレスの区別を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-161">The addressed interface performs the distinction between unicast and anycast addresses as a function of its configuration.</span></span>

<span data-ttu-id="2b3cf-162">一般に、ノードは常にリンク ローカル アドレスを持ちます。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-162">In general, a node always has a link-local address.</span></span> <span data-ttu-id="2b3cf-163">サイト ローカル アドレスおよび 1 つまたは複数のグローバル アドレスを持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b3cf-163">It might have a site-local address and one or more global addresses.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b3cf-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b3cf-164">See also</span></span>

- [<span data-ttu-id="2b3cf-165">インターネット プロトコル バージョン 6</span><span class="sxs-lookup"><span data-stu-id="2b3cf-165">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="2b3cf-166">ソケット</span><span class="sxs-lookup"><span data-stu-id="2b3cf-166">Sockets</span></span>](sockets.md)
