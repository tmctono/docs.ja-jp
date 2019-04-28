---
title: FUSION_INSTALL_REFERENCE 構造体
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 611b4a543a1de7c6163ec45ff7f17d07726569ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936488"
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="5f8d0-102">FUSION_INSTALL_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="5f8d0-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="5f8d0-103">アプリケーションがグローバル アセンブリ キャッシュにアプリケーションがインストールされているアセンブリに参照を表します。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f8d0-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="5f8d0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5f8d0-105">Members</span></span>  
  
|<span data-ttu-id="5f8d0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5f8d0-106">Member</span></span>|<span data-ttu-id="5f8d0-107">説明</span><span class="sxs-lookup"><span data-stu-id="5f8d0-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="5f8d0-108">(バイト単位) 構造体のサイズ。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="5f8d0-109">将来の機能拡張予約されています。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-109">Reserved for future extensibility.</span></span> <span data-ttu-id="5f8d0-110">この値は 0 (ゼロ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="5f8d0-111">このエンティティの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-111">The entity that adds the reference.</span></span> <span data-ttu-id="5f8d0-112">このフィールドは、次の値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="5f8d0-113">-FUSION_REFCOUNT_MSI_GUID:アセンブリは、Microsoft Windows インストーラーを使用してインストールされたアプリケーションで参照されます。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="5f8d0-114">`szIdentifier`にフィールドが設定されている`MSI`、および`szNonCanonicalData`にフィールドが設定されている`Windows Installer`します。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="5f8d0-115">このスキームは、Windows のサイド バイ サイド アセンブリに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="5f8d0-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID:アセンブリが含まれているアプリケーションによって参照される、**プログラムの追加/削除**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="5f8d0-117">`szIdentifier`フィールドを使用してアプリケーションを登録するトークンを提供する、**プログラムの追加/削除**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="5f8d0-118">-   FUSION_REFCOUNT_FILEPATH_GUID:アセンブリは、ファイル システム内のファイルで表されるアプリケーションで参照されます。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="5f8d0-119">`szIdentifier`フィールドは、このファイルへのパスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="5f8d0-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID:アセンブリは、不透明な文字列のみで表されるアプリケーションで参照されます。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="5f8d0-121">`szIdentifier`フィールドは、この不透明な文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="5f8d0-122">この値を削除すると、グローバル アセンブリ キャッシュはあいまいな参照の存在チェックをしません。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="5f8d0-123">-   FUSION_REFCOUNT_OSINSTALL_GUID:この値は予約されています。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="5f8d0-124">アセンブリをグローバル アセンブリ キャッシュにインストールされているアプリケーションを識別する一意の文字列。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="5f8d0-125">その値の値によって異なります、`guidScheme`フィールド。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="5f8d0-126">参照を追加するエンティティのみが認識する文字列。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="5f8d0-127">グローバル アセンブリ キャッシュでは、この文字列が格納されますが、使用しません。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f8d0-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="5f8d0-128">Requirements</span></span>  
 <span data-ttu-id="5f8d0-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f8d0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8d0-130">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5f8d0-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5f8d0-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8d0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8d0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f8d0-132">See also</span></span>

- [<span data-ttu-id="5f8d0-133">Fusion 構造体</span><span class="sxs-lookup"><span data-stu-id="5f8d0-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="5f8d0-134">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="5f8d0-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
