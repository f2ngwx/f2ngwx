# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    =
SPHINXBUILD   = sphinx-build
SOURCEDIR     = source
BUILDDIR      = build
PUBILC      = ..\..\source\doc\how-to-write-makefile

# 根据系统类型选择不同的命令
ifeq ($(OS),Windows_NT)
    # Windows系统下的命令
    COPY = xcopy /e /y /i
else
    # Linux系统下的命令
    COPY = cp -r
endif
# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

# 拷贝文件到目标目录
copy_files:
	$(COPY) "$(BUILDDIR)\html\" "$(PUBILC)"

build: html copy_files
.PHONY: help Makefile build copy_files

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
