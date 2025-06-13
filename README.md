# http-github.com-JR-M29-repo-issue1


describe('saveNote() function', () => {
  it('should save a note with title and content', () => {
    const note = { title: 'Test Note', content: 'This is a test note' };
    saveNote(note);
    expect(localStorage.getItem('notes')).toContain(note.title);
    expect(localStorage.getItem('notes')).toContain(note.content);
  });

  it('should not save a note with empty title', () => {
    const note = { title: '', content: 'This is a test note' };
    saveNote(note);
    expect(localStorage.getItem('notes')).toBeNull();
  });

  it('should not save a note with empty content', () => {
    const note = { title: 'Test Note', content: '' };
    saveNote(note);
    expect(localStorage.getItem('notes')).toBeNull();
  });
});
