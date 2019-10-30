---
title: ASSEMBLY_INFO 構造体
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
ms.openlocfilehash: a43d5e15c02a97ff10a6a5afd439cadebb6b33d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109198"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="68ada-102">ASSEMBLY_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="68ada-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="68ada-103">グローバルアセンブリキャッシュに登録されているアセンブリに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="68ada-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ada-104">構文</span><span class="sxs-lookup"><span data-stu-id="68ada-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="68ada-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="68ada-105">Members</span></span>  
  
|<span data-ttu-id="68ada-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="68ada-106">Member</span></span>|<span data-ttu-id="68ada-107">説明</span><span class="sxs-lookup"><span data-stu-id="68ada-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="68ada-108">構造体のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="68ada-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="68ada-109">このフィールドは、将来の拡張のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="68ada-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="68ada-110">アセンブリに関するインストールの詳細を示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="68ada-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="68ada-111">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="68ada-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="68ada-112">-ASSEMBLYINFO_FLAG_INSTALLED 値。アセンブリがインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="68ada-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="68ada-113">.NET Framework の現在のバージョンでは、常に `dwAssemblyFlags` がこの値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="68ada-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="68ada-114">-アセンブリがペイロード常駐であることを示す ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 値。</span><span class="sxs-lookup"><span data-stu-id="68ada-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="68ada-115">.NET Framework の現在のバージョンでは、この値に `dwAssemblyFlags` が設定されることはありません。</span><span class="sxs-lookup"><span data-stu-id="68ada-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="68ada-116">アセンブリに格納されているファイルの合計サイズ (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="68ada-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="68ada-117">マニフェストファイルへの現在のパスを保持する文字列バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="68ada-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="68ada-118">パスの末尾は null 文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68ada-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="68ada-119">Null 終端文字を含む、`pszCurrentAssemblyPathBuf` 格納されているワイド文字の数。</span><span class="sxs-lookup"><span data-stu-id="68ada-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68ada-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="68ada-120">Requirements</span></span>  
 <span data-ttu-id="68ada-121">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68ada-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68ada-122">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="68ada-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="68ada-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68ada-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ada-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="68ada-124">See also</span></span>

- [<span data-ttu-id="68ada-125">Fusion 構造体</span><span class="sxs-lookup"><span data-stu-id="68ada-125">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="68ada-126">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="68ada-126">Global Assembly Cache</span></span>](../../app-domains/gac.md)
