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
ms.openlocfilehash: 89111bf7eb03d20c2010c7a20c4cd055c2a021e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430735"
---
# <a name="osinfo-structure"></a><span data-ttu-id="d4f50-102">OSINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="d4f50-102">OSINFO Structure</span></span>
<span data-ttu-id="d4f50-103">アセンブリまたはモジュールのオペレーティングシステムの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4f50-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f50-104">構文</span><span class="sxs-lookup"><span data-stu-id="d4f50-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d4f50-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d4f50-105">Members</span></span>  
  
|<span data-ttu-id="d4f50-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d4f50-106">Member</span></span>|<span data-ttu-id="d4f50-107">説明</span><span class="sxs-lookup"><span data-stu-id="d4f50-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="d4f50-108">Microsoft Windows プラットフォーム関数によって定義された識別子の値の1つ `GetVersionEx`。</span><span class="sxs-lookup"><span data-stu-id="d4f50-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="d4f50-109">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d4f50-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="d4f50-110">-VER_PLATFORM_WIN32s、または0x0000。 Microsoft Windows 3.1 を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f50-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="d4f50-111">-VER_PLATFORM_WIN32_WINDOWS、または0x0001 を指定して、Windows 95、Windows 98、またはそれらから派生したオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f50-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="d4f50-112">-VER_PLATFORM_WIN32_NT、または0x0010 を指定して、Windows NT またはそれからのオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f50-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="d4f50-113">オペレーティングシステムのメジャーバージョン。任意のバージョンを示す NULL 値。</span><span class="sxs-lookup"><span data-stu-id="d4f50-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="d4f50-114">オペレーティングシステムのマイナーバージョン。任意のバージョンを示す NULL 値。</span><span class="sxs-lookup"><span data-stu-id="d4f50-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4f50-115">コメント</span><span class="sxs-lookup"><span data-stu-id="d4f50-115">Remarks</span></span>  
 <span data-ttu-id="d4f50-116">`OSINFO` は、Microsoft Windows プラットフォーム関数 `GetVersionEx`の呼び出しで使用される `OSVERSIONINFOEX` の構造に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d4f50-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="d4f50-117">この構造体は、そのオペレーティングシステムのサポートを示すために ASSEMBLYMETADATA 構造体によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f50-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f50-118">要件</span><span class="sxs-lookup"><span data-stu-id="d4f50-118">Requirements</span></span>  
 <span data-ttu-id="d4f50-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f50-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f50-120">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d4f50-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4f50-121">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f50-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4f50-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f50-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f50-123">参照</span><span class="sxs-lookup"><span data-stu-id="d4f50-123">See also</span></span>

- [<span data-ttu-id="d4f50-124">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="d4f50-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="d4f50-125">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4f50-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
