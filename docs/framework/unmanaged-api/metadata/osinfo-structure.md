---
title: OSINFO 構造体
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175227"
---
# <a name="osinfo-structure"></a><span data-ttu-id="00fe2-102">OSINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="00fe2-102">OSINFO Structure</span></span>
<span data-ttu-id="00fe2-103">アセンブリまたはモジュールのオペレーティング システムに関する詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="00fe2-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00fe2-104">構文</span><span class="sxs-lookup"><span data-stu-id="00fe2-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="00fe2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="00fe2-105">Members</span></span>  
  
|<span data-ttu-id="00fe2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="00fe2-106">Member</span></span>|<span data-ttu-id="00fe2-107">説明</span><span class="sxs-lookup"><span data-stu-id="00fe2-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="00fe2-108">Windows プラットフォーム関数`GetVersionEx`で定義された識別子の値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="00fe2-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="00fe2-109">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="00fe2-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="00fe2-110">- VER_PLATFORM_WIN32s、または 0x0000 を使用して、Windows 3.1 を指定します。</span><span class="sxs-lookup"><span data-stu-id="00fe2-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="00fe2-111">- VER_PLATFORM_WIN32_WINDOWS、または 0x0001 を使用して、Windows 95、Windows 98、またはオペレーティング システムを指定します。</span><span class="sxs-lookup"><span data-stu-id="00fe2-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="00fe2-112">- VER_PLATFORM_WIN32_NT、または 0x0002 を使用して、Windows NT またはそこから下位にインストールされたオペレーティング システムを指定します。</span><span class="sxs-lookup"><span data-stu-id="00fe2-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="00fe2-113">オペレーティング システムのメジャー バージョン、または任意のバージョンを示す NULL 値。</span><span class="sxs-lookup"><span data-stu-id="00fe2-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="00fe2-114">オペレーティング システムのマイナー バージョン、または任意のバージョンを示す NULL 値。</span><span class="sxs-lookup"><span data-stu-id="00fe2-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00fe2-115">解説</span><span class="sxs-lookup"><span data-stu-id="00fe2-115">Remarks</span></span>  
 <span data-ttu-id="00fe2-116">`OSINFO`は、 Windows`OSVERSIONINFOEX`プラットフォーム関数`GetVersionEx`の呼び出しで使用される構造に基づいています。</span><span class="sxs-lookup"><span data-stu-id="00fe2-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="00fe2-117">この構造体は、オペレーティング システムのサポートを示すために ASSEMBLYMETADATA 構造体によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="00fe2-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00fe2-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="00fe2-118">Requirements</span></span>  
 <span data-ttu-id="00fe2-119">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00fe2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00fe2-120">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="00fe2-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00fe2-121">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="00fe2-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00fe2-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00fe2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00fe2-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="00fe2-123">See also</span></span>

- [<span data-ttu-id="00fe2-124">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="00fe2-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="00fe2-125">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="00fe2-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
